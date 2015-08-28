
# CONFIG(URATION) FILES
+ http://en.wikipedia.org/wiki/Category:Configuration_files
+ http://en.wikipedia.org/wiki/INI_file

## INI-RC-YAML
+ https://stackoverflow.com/questions/5014632/how-can-i-parse-a-yaml-file-from-a-linux-shell-script
   - https://gist.github.com/pkuczynski/8665367
+ screenrc, http://www.softpanorama.org/Utilities/Screen/screenrc_examples.shtml

----

# PPA
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

# BASH SHELL
+ [ctypes.sh](https://github.com/taviso/ctypes.sh) :: A BASH plugin that provides a foreign function interface directly in your shell. In other words, it allows you to call routines in shared libraries from within bash.
+ https://stribika.github.io/2015/01/04/secure-secure-shell.html

----

# Kernel/ HDD
+ http://www.brendangregg.com/perf.html

----

# REGEX
+ http://en.wikipedia.org/wiki/List_of_Unix_commands
+ http://stackoverflow.com/questions/16956810/finding-all-files-containing-a-text-string-on-linux?rq=1
+ https://en.wikipedia.org/wiki/Regular_expression#Syntax 
+ http://www.theunixschool.com/2012/07/find-command-15-examples-to-exclude.html

----

# Images
+ [Installing Image Magick on Ubuntu 14.04](https://gist.github.com/rodleviton/74e22e952bd6e7e5bee1)

----

# LaTeX
+ Prof. Edward R. Scheinerman's resources to "[Learn LaTeX](http://www.ams.jhu.edu/~ers/learn-latex/)".
+ http://tex.stackexchange.com/questions/8374/the-key-to-understanding-the-latex-syntax
+ latex for MATH: http://en.wikibooks.org/wiki/LaTeX/Mathematics
+ LaTeX tutorial : http://www.pages.drexel.edu/~pyo22/students/latexRelated/latexTutorial.html
+ http://latex-project.org/intro.html

----

# ARBTT 
__desktop timetracker__
+ https://www.joachim-breitner.de/blog/336-The_Automatic_Rule-Based_Time_Tracker
+ GITHUB mirror : 
+ http://arbtt.nomeata.de/#how
+ Install : http://arbtt.nomeata.de/#install
+ Sample Categorize :: http://darcs.nomeata.de/arbtt/categorize.cfg
+ http://stackoverflow.com/questions/20973590/arbtt-nested-if-then-else-in-categorize-cfg/20973950#20973950
+ https://wiki.haskell.org/Unicode-symbols
+ http://darcs.nomeata.de/arbtt/doc/users_guide/arbtt-stats.html#idp213048

----

# Linux : List Open Files for Process
+ http://www.cyberciti.biz/faq/howto-linux-get-list-of-open-files/

