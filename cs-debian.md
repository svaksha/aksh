+ [DEBIAN Packages](#debian-packages)
   + [APT](#apt)
       + [Apt-Pinning](#apt-pinning)
+ [UBUNTU](#ubuntu)
   + [PPA](#ppa)
+ [KDE](#kde)
+ [ISO](#iso)
+ [SUDO](#sudo)
+ [Devices](#devices)
+ [WiFi](#wifi)
+ [DNS](#dns)
+ [GRUB](#grub)
+ [CONFIG](#config)
+ [KERNEL-HDD](#kernel-hdd)
   + [File System](#file-system)
   + [ISO](#iso)
+ [REGEX](#regex)
+ [General](#general)
+ [UTILITIES](#utilities)
   + [Backups](#backups)
   + [Calendar Time Tracker](#calendar-time-tracker)
   + [Editor](#editor)
   + [Spreadsheets](#spreadsheets)
   + [Terminal Multiplexer](#terminal-multiplexer)
+ [Resources](#resources)
+ [systemd](#systemd)

----

+ https://www.debian.org/doc/manuals/debian-faq/ch-choosing.en.html
+ http://wiki.debian.org 
+ http://debian-administration.org 
+ http://askubuntu.com/questions/760204/how-to-remove-the-unity-amazon-package-in-16-04 

# DEBIAN Packages
+ DPKG cheat sheet: http://www.cyberciti.biz/howto/question/linux/dpkg-cheat-sheet.php
+ Syntax 	Description 	Example
+ dpkg -i {.deb package} 	Install the package 	dpkg -i zip_2.31-3_i386.deb
+ dpkg -i {.deb package} 	Upgrade package if it is installed else install a fresh copy of package 	dpkg -i zip_2.31-3_i386.deb
+ dpkg -R {Directory-name} 	Install all packages recursively from directory 	dpkg -R /tmp/downloads
+ dpkg -r {package} 	Remove/Delete an installed package except configuration files 	dpkg -r zip
+ dpkg -P {package} 	Remove/Delete everything including configuration files 	dpkg -P apache-perl
+ dpkg -l 	List all installed packages, along with package version and short description 	dpkg -l ; dokg -l | less ;  dpkg -l '*apache*' ; dpkg -l | grep -i 'sudo'
+ dpkg -l {package} 	List individual installed packages, along with package version and short description 	dpkg -l apache-perl
+ dpkg -L {package} 	Find out files are provided by the installed package i.e. list where files were installed 	dpkg -L apache-perl ; dpkg -L perl
+ dpkg -c {.Deb package} 	List files provided (or owned) by the package i.e. List all files inside debian .deb package file, very useful to find where files would be installed 	dpkg -c dc_1.06-19_i386.deb
+ dpkg -S {/path/to/file} 	Find what package owns the file i.e. find out what package does file belong 	dpkg -S /bin/netstat
dpkg -S /sbin/ippool
+ dpkg -p {package} 	Display details about package package group, version, maintainer, Architecture, display depends packages, description etc 	dpkg -p lsof
+ dpkg -s {package} | grep Status 	Find out if Debian package is installed or not (status) 	dpkg -s lsof | grep Status

## APT
+ http://www.tecmint.com/useful-basic-commands-of-apt-get-and-apt-cache-for-package-management/

#### Apt-Pinning
+ http://wiki.debian.org/AptPinning
+ http://jaqque.sbih.org/kplug/apt-pinning.html

----

# UBUNTU
+ Ubuntu LTS Flavors Comparison: Ubuntu 16.04 vs Kubuntu 16.04 vs Ubuntu GNOME 16.04: http://www.hecticgeek.com/2016/05/ubuntu-16-04-flavors-comparison/
+ http://www.psychocats.net/ubuntu/whichbuntu

## PPA
#### Adding PPA's
1. Add a PPA using APT in terminal by typing the following command: `sudo add-apt-repository ppa:PPA_Name/ppa`

#### Removing PPA's
1. Remove a PPA using APT in terminal by typing the following command: `sudo add-apt-repository --remove ppa:PPA_Name/ppa`
2. Remove a PPA from the source list, else it will get pulled when you update the system.
   + First, find where these PPAs are stored by listing all the PPAs added in your system: `sudo ls /etc/apt/sources.list.d`.
   + Then remove the PPA using the following command: `sudo rm -i /etc/apt/sources.list.d/PPA_Name.list`
3. Remove a PPA by using `ppa-purge` in terminal - What about the applications installed using PPAs? Will they be removed as a result of removing the PPA? The answer is NO. So, we use `PPA purge` to remove the PPA and uninstall all the programs installed by the PPA.
   + Install ppa-purge with this command: `sudo apt-get install ppa-purge`
   + Then use it to purge the PPA: `sudo ppa-purge ppa-url` {{The URL of the PPA can be found in the Software Sources list.}}

----

# KDE 

## Dual Desktop Environment - KDE + Gnome
+ Install KDE plasma5 instead of Gnome: http://www.tecmint.com/install-kde-plasma-5-in-linux/
+ http://askubuntu.com/questions/417/how-do-i-install-kde
+ http://askubuntu.com/questions/691331/ended-up-having-kde-4-x-plasma-4-instead-of-plasma-5-4-from-ubuntun-14-04
+ http://www.howtogeek.com/193129/how-to-install-and-use-another-desktop-environment-on-linux/
+ http://www.linuxandubuntu.com/home/5-best-linux-desktop-environments-with-pros-cons

### HDD
+ KDE Partition Manager , https://www.kde.org/applications/system/kdepartitionmanager/


----

# ISO
## ISO - Debian
+ http://cdimage.debian.org/debian-cd/current-live/amd64/iso-hybrid/
+ https://www.debian.org/CD/faq/#write-usb
+ Debian ISO, https://www.debian.org/CD/

## ISO - Ubuntu
+ http://releases.ubuntu.com/
+ Ubuntu iso via wget, https://askubuntu.com/questions/305304/download-13-04-iso-with-wget
+ 64-bit Vs. 32-bit, https://superuser.com/questions/238112/what-is-the-difference-between-i686-and-x86-64

### multiboot iso
+ SARDU, http://www.howtogeek.com/howto/39880/how-to-combine-rescue-disks-to-create-the-ultimate-windows-repair-disk/
+ MultiCD, https://github.com/IsaacSchemm/MultiCD
   + http://multicd.us/#Instructions
+ https://askubuntu.com/questions/46624/how-to-create-a-bootable-usb-with-multiple-iso-images-in-it
+ https://ubuntuforums.org/showthread.php?t=1071869


----

# SUDO
### Adding users to sudoers group
$ groups        # check if the user is in the sudoers file 
$ less /etc/passwd    # check if the user is in the sudoers file 
$ sudo visudo       # visudo tool can also check the sudoer group
$ nano /etc/group   # now add the user to the sudoer file with nano.

----

# Devices

### delete contents of USB
$ fdisk -l
$ dd if=debian.iso of=/dev/sdX   # X is replaced by `sda`

+ How to force format a USB device?, https://ubuntuforums.org/showthread.php?t=2030703&page=2 

### Dual monitor
+ How to configure multiple displays on a Dell PC using the Ubuntu operating system, http://www.dell.com/support/article/de/de/dedhs1/SLN298529/en
+ http://www.thegeekstuff.com/2009/08/ubuntu-tips-how-to-setup-dual-monitor/

----

# WiFi

### WIFI realtek firmware for Debian
$ dmesg    # list devices
$ mount    # mounts a device (like USB)
$ sudo mount /dev/sdb1 /mnt      # mount the USB stick.
$ ls /mnt              # list mounted devices.
$ cp /mnt/firmware-realtek_0.43_all.deb /var/tmp     # copies the WIFI realtek firmware debian library to the /var temp lib.
$ sudo dpkg -i /var/tmp/firmware-realtek_0.43_all.deb  # update the firmware from the debian repository.

+ https://wiki.debian.org/rtl819x
+ http://www.linux.org/threads/fixing-broadcom-and-realtek-wireless-issues.7685/

----

# DNS
+ http://www.thekelleys.org.uk/dnsmasq/doc.html
+ https://hackercodex.com/guide/how-to-stop-isp-dns-server-hijacking/
+ http://askubuntu.com/questions/708762/redirecting-to-http-domain-error-com
+ dont use opendns : http://www.cyberciti.biz/tips/opendns-sucks.html

----

# GRUB
+ https://help.ubuntu.com/community/DataRecovery

### grub rescue mode
+ grub rescue, https://www.howtoforge.com/tutorial/repair-linux-boot-with-grub-rescue/
+ How to Rescue a Non-booting GRUB 2 on Linux, https://www.linux.com/learn/tutorials/776643-how-to-rescue-a-non-booting-grub-2-on-linux/
+ https://www.linux.com/learn/tutorials/809671-get-your-data-back-with-linux-based-data-recovery-tools
+ https://www.howtoforge.com/tutorial/repair-linux-boot-with-grub-rescue/
    + Basic Commands: https://www.howtoforge.com/tutorial/repair-linux-boot-with-grub-rescue/#basic-commands-available
+ http://www.cgsecurity.org/wiki/TestDisk
+ http://askubuntu.com/questions/142300/fixing-grub-error-error-unknown-filesystem/179662#179662
+ http://askubuntu.com/questions/493826/grub-rescue-problem-after-deleting-ubuntu-partition
+ HOWTO : [Boot & Install Ubuntu from the Grub Rescue Prompt](https://ubuntuforums.org/showthread.php?t=1599293)
+ http://www.supergrubdisk.org/
+ https://help.ubuntu.com/community/Grub2/Troubleshooting
+ http://itsfoss.com/solve-error-partition-grub-rescue-ubuntu-linux/
+ Recovering a deleted partition table: http://tldp.org/HOWTO/Partition/recovering.html

----

# CONFIG

+ Stow: https://www.gnu.org/software/stow/
+ http://en.wikipedia.org/wiki/Category:Configuration_files
+ http://en.wikipedia.org/wiki/INI_file

## Config-Git
+ https://stackoverflow.com/questions/21249071/where-do-you-store-your-gitconfig-file
+ https://stackoverflow.com/questions/11786623/cant-hard-link-the-gitconfig-file

## INI-RC-YAML
+ https://stackoverflow.com/questions/5014632/how-can-i-parse-a-yaml-file-from-a-linux-shell-script
   - https://gist.github.com/pkuczynski/8665367
+ screenrc, http://www.softpanorama.org/Utilities/Screen/screenrc_examples.shtml

----

# KERNEL-HDD
+ http://www.brendangregg.com/perf.html
+ Initramfs, https://en.wikipedia.org/wiki/Initramfs
+ [RecuperaBit](http://www.kitploit.com/2016/11/recuperabit-tool-for-forensic-file.html) - A Tool For Forensic File System Reconstruction.

### Ubuntu Cloud Snappy
+ https://askubuntu.com/questions/620996/how-to-install-snappy-ubuntu-15-04-core-images-on-a-pc
+ http://www.ubuntu.com/cloud/tools/snappy
+ https://wiki.ubuntu.com/Core

----

# REGEX
+ RegEX cheatsheet, https://remram44.github.io/regex-cheatsheet/regex.html
+ [awesome-regex](https://github.com/aloisdg/awesome-regex) :: A curated collection of Regular Expressions libraries, tools, frameworks and software. 
+ http://en.wikipedia.org/wiki/List_of_Unix_commands
+ http://stackoverflow.com/questions/16956810/finding-all-files-containing-a-text-string-on-linux?rq=1
+ https://en.wikipedia.org/wiki/Regular_expression#Syntax
+ http://www.theunixschool.com/2012/07/find-command-15-examples-to-exclude.html

----

# General
+ List Open Files for Process, http://www.cyberciti.biz/faq/howto-linux-get-list-of-open-files/
+ http://askubuntu.com/questions/240857/what-commands-will-change-my-screens-brightness
+ [Installing Image Magick on Ubuntu 14.04](https://gist.github.com/rodleviton/74e22e952bd6e7e5bee1)
+ https://github.com/ewiger/findtools
+ 16 commands to check hardware information on Linux: http://www.binarytides.com/linux-commands-hardware-info/

----

# UTILITIES

## Backups
+ [attic](https://github.com/jborg/attic) :: Deduplicating backup program. [Docs](https://attic-backup.org/).
+ https://github.com/xolox/python-rotate-backups
+ BakThat : https://github.com/tsileo/bakthat __{Status : UnMaintained}__
+ rsync, http://www.mikerubel.org/computers/rsync_snapshots/
+ storelet : https://pypi.python.org/pypi/storelet

+ http://stackoverflow.com/questions/123198/how-do-i-copy-a-file-in-python
+ http://stackoverflow.com/questions/3207219/how-to-list-all-files-of-a-directory-in-python
+ http://codereview.stackexchange.com/questions/49351/python-back-up-script

## Calendar Time Tracker 
+ Toggl: https://github.com/toggl/ and https://github.com/toggl/toggldesktop
+ https://github.com/search?utf8=%E2%9C%93&q=calendar, in [Ruby](https://github.com/search?l=Ruby&q=calendar&type=Repositories&utf8=%E2%9C%93) and [Python](https://github.com/search?l=Python&q=calendar&type=Repositories&utf8=%E2%9C%93).
+ https://www.linux.com/learn/five-best-open-source-calendar-servers-linux
+ https://sourceforge.net/directory/business-enterprise/scheduling/calendar/language%3Ajava/os%3Alinux/
+ http://www.techsupportalert.com/best-free-reminder-to-do-program.htm

#### Arbtt desktop timetracker
+ https://www.joachim-breitner.de/blog/336-The_Automatic_Rule-Based_Time_Tracker
+ http://arbtt.nomeata.de/#how
+ Install : http://arbtt.nomeata.de/#install
+ Sample Categorize :: http://darcs.nomeata.de/arbtt/categorize.cfg
+ http://stackoverflow.com/questions/20973590/arbtt-nested-if-then-else-in-categorize-cfg/20973950#20973950
+ https://wiki.haskell.org/Unicode-symbols
+ http://darcs.nomeata.de/arbtt/doc/users_guide/arbtt-stats.html#idp213048

#### [OrangeScrum](http://www.orangescrum.org/)
+ Download source code: https://github.com/Orangescrum/orangescrum

## Editor

#### Edit PDF
+ http://askubuntu.com/questions/16652/which-programs-can-i-use-to-edit-pdf-files
+ http://askubuntu.com/questions/162037/how-to-edit-pdfs

## Spreadsheets
+ [roo](https://github.com/roo-rb/roo) :: An interface to spreadsheets of several sorts. 

## Terminal Multiplexer

### [Screen](https://en.wikipedia.org/wiki/GNU_Screen)

### [Tmux](https://en.wikipedia.org/wiki/Tmux)
+ Rik's conf: http://www.rikrose.net/tmux.conf

----

# Resources
+ https://help.ubuntu.com/community/SoftwareManagement
+ https://github.com/aleksandar-todorovic/awesome-linux/
+ Scrapers: https://github.com/cassidoo/scrapers

----

# systemd
+ https://www.freedesktop.org/wiki/Software/systemd/
+ Python bindings: https://www.freedesktop.org/software/systemd/python-systemd/index.html
