# Topic 2: Useful Python Tools

One of the great beneftis of Python, particularly in astronomy, is that it is relatively easy to write and import bespoke tools for tasks at hand. This also means that there are large open source collaborative efforts to produce Python tools that are free to use and great for research!

In this tutorial, we're just going to be introduced to some of the commonly used tools in astronomy, through a plotting exercise. This is absolutely not a comprehensive list, just some tools that I frequently use and would like to share with you!

## The tools
A list of all the packages you'll want to install are below:  
[numpy](https://numpy.org/)  
NumPy is one of the fundamental packages for Python (and without it, most of this programming language would crumble). It allows for fast arithmetic and use of arrays, which are ubiquitous in modern scientific analyses. No Python script is complete without it.

[matplotlib](https://matplotlib.org/)  
Matplotlib is the bread and butter of plotting in Python. Originally a Python version of MatLab's plotting tools, it has since expanded to cover an incredibly broad range of applications. Getting to grips with the ins and outs of matplotlib is an important part of preparing any scientific plot.


[pandas](https://pandas.pydata.org/docs/user_guide/index.html)  
Pandas is another important and influential Python package. It's a fast and flexible data manipulation tool, which also includes data analysis tools (although I don't use them much, personally). I've heard it described to me as excel but in Python, which is a good way to view it (and it reads in excel files excellently, too). Getting to grips with Pandas is a worthwhile endeavour early in an academic career.


[seaborn](https://seaborn.pydata.org/)  
Seaborn is another plotting library--- but it doesn't replace matplotlib. Instead, it complements it! Seaborn is specifically intended as a statistical plotting library, and is incredibly useful when plotting distributions in particular. It also has a ton of pre-set options for how your plots are displayed that are a little harder to achieve in vanilla matplotlib (with as little effort, that is). Especially useful is also it's colour palettes, which you can also pre-set to be colour-blind friendly. I use seaborn all the time, and I recommend you do too!

[astropy](https://www.astropy.org/)  
Astropy is (I believe) the biggest collaborative Python package in astronomy, encompassing a very broad range of tools, functions, and standards. Just look at [their gigantic list of tutorials](https://learn.astropy.org/tutorials.html)! Personally, I tend to use Astropy for astronomical constants, downloading data, and working with time-series photometry. However it is also full of tools to use with astronomical observatiosn specifically, which I have less experience in myself. I really recommend you check out the tutorials linked above for Astropy functions that fit your science interests!

(...and one more just because)  
[lightkurve](https://docs.lightkurve.org/)  
Lightkurve is an awesome tool for working with *Kepler* and *TESS* data, full of functions that let you tidy up the data, look for transits, and study asteroseismic signals. I'm plugging it here a little bit because I've worked on it, but mostly because its an excellent example of how collaborative open source Python programming works in motion. I highly recommend checking it out, along with Topic 3, if you're interested.

## The Tutorial
In this folder of the repository you will find two Jupyter Notebook. Clone the repository to your own computer (check out Topic 1 for how to do this). The Jupyter Notebook titled `tutorial_blank.ipynb`, and not the other one yet (which has the answers!). See below on how to install Jupyter Notebooks, if you haven't already.

Make your way through the tutorial bit by bit. If you're stuck, check out the `tutorial_answers.ipynb` file, so you can see what I did to work with the data at each step.


## Jupyter Notebooks

In order to work with this tutorial on your computer, you're going to have to install Jupyter Notebooks, if you haven't done so already. Jupyter Notebook comes pre-packaged with Anaconda, if you have that installed. To open Jupyter Notebook, you just type:

```
jupyter notebook &
```

in commandline. This opens a Jupyter Notebook in a browser terminal (although it's not online, it just uses a browser to work). If you don't use Anaconda (and don't have Jupyter installed), you can do so as follows:

```
pip3 install --upgrade pip
pip3 install jupyter
```
