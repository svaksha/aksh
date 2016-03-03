+ [DEB Packages](#deb-packages)
   + [PPA](#ppa)
+ [ISO](#iso)

----

# DEB Packages
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

# ISO
+ http://cdimage.debian.org/debian-cd/current-live/amd64/iso-hybrid/
