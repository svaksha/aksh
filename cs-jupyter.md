+ [Magic Commands](#magic-commands)
+ [NB Extensions](#nb-extensions)
+ [Julia Bugs](#julia-bugs)
+ [Resources](#resources)

----

+ jakevdp blogs about [Conda: Myths and Misconceptions](https://jakevdp.github.io/blog/2016/08/25/conda-myths-and-misconceptions/).


----

# Magic Commands
+ [Advanced Jupyter Notebook Tricks — Part I](http://blog.dominodatalab.com/lesser-known-ways-of-using-notebooks/)
+ [Cell-magic](https://ipython.readthedocs.org/en/stable/interactive/magics.html#cell-magics) and [Built-in magic commands](https://ipython.readthedocs.org/en/stable/interactive/magics.html).
+ https://github.com/DELabUW/szkola-letnia-2015/blob/master/zajecia/deser_r_ggplot.ipynb

----

# NB Extensions
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

# Julia Bugs
+ Proper method for including external JS libraries?, https://github.com/JuliaLang/IJulia.jl/issues/345
+ IJulia Errors "load failed, save is disabled" in 0.5-dev despite making the notebook "trusted" : https://github.com/JuliaLang/IJulia.jl/issues/252
+ Allow multiple versions of Julia as IPython kernels: https://github.com/JuliaLang/IJulia.jl/pull/280
    + https://github.com/JuliaLang/IJulia.jl/issues/224
+ IJulia / IPython / Jupyter combination not working #289: https://github.com/JuliaLang/IJulia.jl/issues/289
+ http://stackoverflow.com/questions/24091373/best-way-to-run-julia-code-in-an-ipython-notebook-or-python-code-in-an-ijulia-n

----

# [Resources](https://github.com/svaksha/pythonidae/blob/master/Utilities.md#jupyter)
+ [Running Jupyter with multiple Python and iPython paths](http://stackoverflow.com/questions/39007571/running-jupyter-with-multiple-python-and-ipython-paths/).
