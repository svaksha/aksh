+ [Jupyter](#jupyter)
+ [NLP](#nlp)
+ [HDF5](#hdf5)
+ [MOOC](#mooc)

====

+ Python is easier to learn than C/C++, http://neverworkintheory.org/2014/01/29/stefik-siebert-syntax.html

----

# Jupyter
https://github.com/ipython-contrib/IPython-notebook-extensions, allows you to install some very useful extensions for the Jupyter notebook. One of the extension allows for copy pasting cells across notebooks and picture into a notebook. Here is an installation script used to install the notebook extensions within he Anaconda/Miniconda distribution:

'''
using PyCall
if PyCall.conda
	using Conda
	conda = Conda.conda
else
	conda = "conda"
end
dir = mktempdir()
cd(dir) do
	run(`git clone https://github.com/ipython-contrib/IPython-notebook-extensions`)
	run(`$conda install conda-build`)
	run(`$conda build IPython-notebook-extensions`)
	run(`$conda install --use-local nbextensions`)
end
rm(dir, recursive=true)
'''

After installation go to `http://localhost:8888/nbextensions` and activate the extensions you like.

----

# NLP
+ http://NLTK.org

----

# HDF5
+ https://github.com/h5io/h5io

----

# Build

## setup.py
+ https://github.com/cobbler/cobbler/blob/master/setup.py
+ https://docs.python.org/3.4/distutils/setupscript.html
+ http://stackoverflow.com/questions/5932804/set-file-permission-in-setup-py-file/25761434#25761434

## Conda
+ http://conda.pydata.org/docs/intro.html#conda-overview

----

# Julia-via-Anaconda
+ https://groups.google.com/forum/#!topic/julia-dev/-B90BrkzM6E
+ https://github.com/JuliaLang/IJulia

----

# Tox
+ https://testrun.org/tox/latest/example/basic.html#depending-on-requirements-txt
+ https://testrun.org/tox/latest/config.html

----


# MATH
+ http://stackoverflow.com/questions/7160926/how-to-solve-an-integral-equation-in-python
+ http://stackoverflow.com/questions/16275352/how-to-solve-integration-using-simpsons-rule-in-python

----

# Programming

## Exceptions
+ http://stackoverflow.com/questions/21211006/how-to-catch-all-old-style-class-exceptions-in-python

## Classes
+ http://lucumr.pocoo.org/2013/2/13/moar-classes/

## schedule tasks
+ http://www.fbeedle.com/python/99-6ch02.pdf

## BAD programming habits
+ http://stackoverflow.com/questions/21553327/why-is-except-pass-a-bad-programming-practice

## Interactive Python
+ http://www.codeskulptor.org/coursera/syllabus.html
+ Ex:  http://www.codeskulptor.org/#user2-T5HQQkgicddJyTs-0.py

## MOOC
+ MIT's "gentle" introduction to Python : http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-189-a-gentle-introduction-to-programming-using-python-january-iap-2011/
+ MIT's Python class: http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-189-a-gentle-introduction-to-programming-using-python-january-iap-2011/
+ Think Python: http://greenteapress.com/thinkpython/thinkpython.html
+ Codingbat: Online test cases to practice python and Java, http://codingbat.com/

