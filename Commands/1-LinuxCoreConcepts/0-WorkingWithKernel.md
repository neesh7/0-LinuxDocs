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