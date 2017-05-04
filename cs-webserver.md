+ [Frameworks](#frameworks)
+ [Flask](#flask)
+ [Jekyll](#jekyll)
+ [Web](#web)
+ [Security](#security)
+ [HCI](#hci)
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

# Frameworks
+ http://www.devx.com/webdev/create-your-own-mvc-framework.html
+ http://blog.chartbeat.com/2013/06/04/great-hack-writing-an-mvc-framework-from-scratch/
+ http://www.codeproject.com/Articles/25057/Simple-Example-of-MVC-Model-View-Controller-Design
+ Web scraping framework: http://blog.adnansiddiqi.me/tag/scraping/

----

# Flask
+ PDF: https://www.tutorialspoint.com/flask/flask_tutorial.pdf
+ Video of Python Tutorial: Creating Web Sites using Python and Flask:: https://www.youtube.com/watch?v=M1IVwFAH9Wo
+ https://www.quora.com/What-are-best-resources-to-learn-Flask
+ Flask by Example - [Implementing a Redis Task Queue](https://realpython.com/blog/python/flask-by-example-implementing-a-redis-task-queue/) :: This part of the tutorial details how to implement a Redis task queue to handle text processing.
+ Creating your first web app with Python/Flask: https://www.forbeginners.co/python/flask/creating-first-web-app-python-flask/
+ [Flask-Script](https://flask-script.readthedocs.io/en/latest/) extension provides support for writing external scripts in Flask. This includes running a development server, a customised Python shell, scripts to set up your database, cronjobs, and other command-line tasks that belong outside the web application itself.
+ [Emails](https://pythonhosted.org/flask-mail/), [documentation](https://flask-mail.readthedocs.io/en/latest/).
+ http://pythonhow.com/your-first-flask-website
+ How to write a web service using Python Flask: https://opensource.com/article/17/3/writing-web-service-using-python-flask

## Docs
+ http://flask.pocoo.org/docs/0.12/quickstart/
+ http://flask.pocoo.org/docs/0.12/patterns/fileuploads/
+ Configuration Handling: http://flask.pocoo.org/docs/0.12/config/
+ Wrapper for passing [command-line flags](http://flask.pocoo.org/snippets/133/) to `app.run()` in Flask.
+ http://flask.pocoo.org/docs/0.12/patterns/urlprocessors/
+ https://realpython.com/blog/python/introduction-to-flask-part-2-creating-a-login-page/

## YAML
+ [flask-swagger](https://github.com/gangverk/flask-swagger) :: Flask-swagger provides a method (swagger) that inspects the Flask app for endpoints that contain YAML docstrings with Swagger 2.0 Operation objects.
+ [Flask-Fixtures](https://github.com/croach/Flask-Fixtures] :: A simple library for adding database fixtures for unit tests using nothing but JSON or YAML.

----

# Jekyll
+ https://www.smashingmagazine.com/2014/08/build-blog-jekyll-github-pages/
+ source on [github](https://github.com/jekyll/jekyll) and the [yaml frontmatter](https://jekyllrb.com/docs/frontmatter/).

----

# Static Sites

## HuGo
+ A Fast and Flexible Static Site Generator built with love by spf13 and friends in Go: https://github.com/spf13/hugo


----

# Security
+ [Python for metasploit Automation](http://www.primalsecurity.net/python-for-metasploit-automation/).
+ XSS = Cross-site scripting, https://en.wikipedia.org/wiki/Cross-site_scripting
+ https://en.wikipedia.org/wiki/Category:Injection_exploits



