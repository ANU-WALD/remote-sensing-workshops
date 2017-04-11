# remote-sensing-workshops

2017 workshop activities for [ENVS3109](http://programsandcourses.anu.edu.au/course/ENVS3019)
(other content online [here](http://wenfo.org/wald/advanced-remote-sensing))

In each workshop, you work through that week's exploratory analysis
using Python in an interactive [Jupyter Notebook](https://jupyter.org/).
After an introduction to Python, each week will demonstrate a technique you
can use to analyse remote sensing data with an example dataset.


Date | Topic | Techniques | Data
--- | --- | --- | ---
18 Apr | Introduction to Python | syntax and basic usage (see 'software carpentary' below for more) | N/A
02 May | Image analysis | file formats, loading data, colour scales, combining bands, indices | Aerial photos of ANU
02 May | Change Detection | thresholds, difference between images, selecting data, means and variance, OPeNDAP | TBD - 2003 fires?
09 May | Trend Analysis | 'data cubes', reduction to timeseries, time-dim summaries, uneven spacing, plots | Vegetation indicies
16 May | Combining Vector and Gridded Data | TBD | TBD
23 May | Correlation Analysis | TBD | TBD

Depending on student interest, a number of optional workshops may be organised to cover important tools for writing software (version control with Git, intro to software testing), general data analysis and graphing (how to ditch Excel), and how to use and contribute to open-source projects (plus: what is open source anyway?).


## Useful links

- [Anaconda](https://continuum.io/downloads) is like Python, but larger: it comes with many scientific packages built-in and makes it far easier to install others.  If you want to use Python for science, you should install the latest version of Anaconda - it's available for every operating system and entirely free.

- [Software Carpentry](https://software-carpentry.org/lessons/) provide excellent introductions to programming for scientists.  You can read the material online, or attend a workshop at many scientific conferences.

- [*Think Python* 2nd ed.](http://greenteapress.com/wp/think-python-2e/) is the best introductory Python textbook I've found.  And it's entirely free.

- [GitHub](https://github.com/) provides free hosting and collaboration tools, making it the world's largest repository of open source software.  With an account, you can manage your own work using Git - and read the source of or contribute to any of the tools we'll use, from this document to Python itself.

- The Jupyter project has an [incredible list of notable Notebooks](https://github.com/jupyter/jupyter/wiki/A-gallery-of-interesting-Jupyter-Notebooks) which you can read online or download and run for yourself.  The [Python for Geosciences](https://github.com/koldunovn/python_for_geosciences) and [Earthpy](http://earthpy.org/) collections are particularly relevant (in that order).


## Using Jupyter Notebooks

Instead of the (many) useful and powerful features, this section just describes how to get the notebooks in this directory running.

- Have Anaconda installed on the computer.  (If you're in an ANU computer lab, it should be)
- Open a terminal.  On Windows, you can open a terminal in any folder by opening it in the file explorer, clicking the address bar, and typing `cmd` and enter.
- In the terminal, type `jupyter notebook` and the notebook homepage will open, and you can navigate to the notebook you want.  Alternatively, type `jupyter notebook <name of notebook>` to open it directly.  Note that pressing the tab key completes a partial filename, so you can just type `jupyter notebook 1<tab>` to open the first notebook.

Note that after the first workshop (intro to Python), you will need to

### *A brief digression on scientific software*

Programming languages and tools are generally classified on a (subjective) spectrum:

- at a low level, you give detailed instructions and think like a computer
- at a medium level, you give instructions in a more natural language (which someone else implemented below)
- at a high level, you simply declare what you want and it happens (thanks to someone else below)

The tradeoff is computer performance (low-level) against human performance (high-level) - and with the speed of modern computers you should generally use the highest-level tools available.
Installing existing software avoids the need to reinvent decades of useful functionality.

In Python, the best way to install scientific packages is the `conda` install tool in [Anaconda](https://www.continuum.io/downloads).  Anaconda just like a Python, but bigger - because it's got many science tools by default.

Since we're using some specialist tools for geospatial data, we'll use `conda` to create a new environment with everything we need (installing too many Python pacakges into one environment leads to [dependency hell](https://en.wikipedia.org/wiki/Dependency_hell)).

First, check whether the `remote-sensing` environment already exists by opening a terminal (windows key, then type "cmd" and enter) and running the following command:

    conda env list

If `remote-sensing` isn't in the list, run the following command (remember you can right-click and paste a command):

    conda create -n remote-sensing -c conda-forge xarray netcdf4 numpy bottleneck cartopy seaborn dask jupyter_core
