## Package Management In Linux
```bash
# There are mostly 2 types of linux distro categorization based on package managers
# 1. Rpm based(RHEL, CentOS, Fedora)
# 2. debian based( Ubuntu, Debian, Linux Mint)

# Different package manager in linux - DPKG, APT, APT-GET, RPM, YUM, DNF

```
## Redhat Package manager(RPM)
![alt text](Images/RPM.png)

## Yellowdot Update Modify Package Manager (YUM)
 - Works with RPM Based distros
 - High level package manager which does automatic dependency resolution
 - software repos
![alt text](Images/YUM.png)
```bash

$ yum repolist # will show all repolist added to system
$ yum provides scp 
$ yum install httpd # to install a package
$ yum remove httpd # to uninstall 
$ yum update telnet # to update a package
$ yum update # will check and update all packages
```