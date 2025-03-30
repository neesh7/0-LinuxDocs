## Commands
### Working with the Kernel - I
```bash
$ uname # to get linux kernel details
$ uname -r # to get kernel version
$ uname -a

$ dmesg # display msg from kernel [ring buffer]
$ dmesg | grep -i usb # here we can see msg if we add any usb

# udevadm is a utility manager tool for udev (user space device manager daemon)

$ udevadm info --qeuery=path --name = /dev/sda5 # queries udev database for device info
$ udevadm monitor # listens to kernel uevent

$ lspci # lists info of all pci devices configured in system
# pci devices - ethernet card, rate controller, video cards and wireless adapters

$ lsblk # lists infor about block devices / hardisk partitions
# Major 1--> RAM, Major 3 --> Hardisk/Cd-rom, Major 6 --> parallel printers, Major 8 --> SCSI disk

$ lscpu # to display info about cpu architechture
$ lsmem # to list available memory in system
$ lsmem --summary

$ free -m # display memory info in mb
$ free -g # display memory info in gb
$ free -k # display memory info in kb

$ lshw # tool to extract info about harware of system
$ sudo lshw
```

### Linux Boot Process
```
When we start or restart the linux machine what happens.

BIOS POST --> Boot Loader (Grub2) --> Kernel Initiallization --> Init Process --> SystemD

1. BIOS POST
    - BIOS(basic input output system) POST (Power on self test).
    - BIOS runs a self test to ensure all attached hardware is functioning properly 
      if not it concludes machine is faulty.

2. Boot Loader (GRUB2)
    - executes boot code from hardisk which is available at /boot filesystem in linux.
      once done it loads linux kernel into memory

3. Kernel Initiallization
    - During this phase, kernel is Initiallized by decompressing the kernel code.
    - kernel then runs several task like Initiallizating hardware & memory management task and so on.

4. Init Process (SystemD Init System / SysV Init System)
    - Service Initiallization, Init sets up user space and environment required for user env.
    - After that, Init calls SystemD daemon which is responsible to prepare linux to usable state.

Note: SystemD is responsible for mounting file system, starting and managing system services.
```
```bash
$ ls -l /sbin/init #to check if it uses systemD/SysV Init System
```
#### Runlevels
```
Runlevels --> Only valid for those system which have SysV init System. It is not valid for SystemD Init System.

In traditional Linux systems that use the SysV init system, a runlevel defines the state of the system and determines which services are started and available. Think of it as different operating modes of the system.

# Note:
The term runlevels is used in the sysV init systems. These have been replaced by systemd targets in systemd based systems.

The complete list of runlevels and the corresponding systemd targets can be seen below:

runlevel 0 -> poweroff.target

runlevel 1 -> rescue.target

runlevel 2 -> multi-user.target

runlevel 3 -> multi-user.target

runlevel 4 -> multi-user.target

runlevel 5 -> graphical.target

runlevel 6 -> reboot.target
```
```bash 
$ runlevel # during boot process init system checks run levels

# In systemD based Init system we can check states of system using systemctl instead of runlevels
$ systemctl get-default # shows system states for systemD based init system
$ ls -ltr /etc/systemd/system/default.target # Checking default target
$ systemctl set-default multi-user.taregt # Updating deault target
```