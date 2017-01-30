+ [HCI](#hci)
+ [Web-Security](#web-security)
+ [WEB](#web)

----

# HCI
+ SIG local chapter of http://www.sigchi.org/connect/local-sigs
+ HCI Lecture notes : http://www.cs.cmu.edu/~bam/uicourse/08763fall15/
+ Human Factors in Aviation Safety : http://www.faa.gov/aircraft/air_cert/design_approvals/human_factors/
+ Human Factors in Aviation Maintenance : http://www.faa.gov/regulations_policies/handbooks_manuals/aircraft/media/amt_handbook_addendum_human_factors.pdf
+ Human Factors Design Guidelines for Multifunction Displays : http://www.faa.gov/data_research/research/med_humanfacs/oamtechreports/2000s/media/0117.pdf

----

# WEB
## Migrating from Windows to LAMP stack

L = Linux
A = Apache
M = MySQL/MariaDB
P = Perl/PHP/Python

1.  First Migrate the Database data
Try to copy schema as much as possible, run lots of test queries on new DB, determine where the differences are (are primary keys defined differently?
Are some field definitions different? Are dates formatted differently?) that kind of stuff.  

2.  Write all your existing website database calls in your chosen language for your new database.  Fix anything that doesn't work.
One of the biggest gotchas in moving from Windows to Linux is case
sensitivity in file names.  I always, always use all lower case file
names specifically to avoid this problem. Links to File.html and
file.html do not look for the file on Linux like they will on Windows.
So even if you lower case all the file names, you still have to find
the references in the code and fix those as well.

3.  Especially check the calls that take in new data and make sure the input
is formatted properly for the new database.  Ensure that anywhere you allow
input that goes into the database - that you have secure practices that
restrict the input to safe data.
SQL syntax is difference if you are moving from MSSQL to mysql, so
some queries may need to be revised.

4.  Take your collection of queries and notes about what is different and start building your webpages around it.    Do you have a new style or are you copying the style from the existing webpages? You can "view source" on the pages and grab the static html and use that to help write your dynamic code.

5.  Fit your webpages into the style template that either you have created for them or that has been provided to you. It helps to have at least one person on staff, or at least available for consulting) who knows both sides of the transition .NETand PHP, MSSQL and mysql.

----

# Web-Security
+ XSS = Cross-site scripting, https://en.wikipedia.org/wiki/Cross-site_scripting
+ https://en.wikipedia.org/wiki/Category:Injection_exploits

----

