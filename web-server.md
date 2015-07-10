A collection of tips and tricks.

# Migrating from Windows to LAMP stack

L = Linux
A = Apache
M = MySQL/MariaDB
P = Perl/PHP/Python

1.  First Migrate the Database data
Try to copy schema as much as possible, run lots of test queries on new DB,
determine where the differences are (are primary keys defined differently?
Are some field definitions different? Are dates formatted differently?)
that kind of stuff. 
Make sure you will not need to use any Windows or .Net specific
objects.  This happens with sites running .Net that use Windows
objects for functionality like reading spreadsheets or word processing
documents.  Windows objects will  not run natively on Linux boxes.
Sometimes you can get them to work, but it is NEVER easy..

2.  Write all your existing website database calls in your chosen language
for your new database.  Fix anything that doesn't work.
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

4.  Take your collection of queries and notes about what is different and
start building your webpages around it.    Do you have a new style or are
you copying the style from the existing webpages?
You can "view source" on the pages and grab the static html and use that to
help write your dynamic code.
There is a steep learning curve for moving from WM.N to LAMP
...especially for .Net developers.  Lots of differences in the process
and the syntax.  I've been moving between them for years, and I still
occasionally get confused or forget some major requirement.  It can be
extremely frustrating, especially if you are dealing with  a poorly
documented Source CMS,  Configuration can be issue as well file
permissions and other issues that devs working in Windows don't
encounter.
(if you want to weed out those who do not have skills to make the
jump, ask them "where in the Linux directory structure does web root
live".  If they can't answer, it will take them a very long time to
catch up on the Linux environment.)

5.  Fit your webpages into the style template that either you have created
for them or that has been provided to you.
It helps to have at least one person on staff, or at least
available for consulting) who knows both sides of the transition.  NET
and PHP . MSSQL and mysql.or

