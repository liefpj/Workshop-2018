# BD2K Summer Coding Workshop 2018
Welcome! The goal of this workshop is to get your Python environment up to speed. We will discuss useful coding tools, environments, and structuring a project. There isn't one way or even a common standard. One of the great things about open source software is you can take this information and modify it to suite your needs. The internet is also your best friend for learning when it comes to writing software. Just type your question into Google and you will find your answer more often than not. 

One of the challenges with these workshops is dealing with operating systems. The way you will install software will change depending on your operating system. Since this has been a problem for a long time, there is fortunately a set of tools that will help us work across systems. The first thing we need to do is download the code we will be working with.


## Install Git (5 min)
Github is a website to store and distribute software. Github is based on the popular version control system called git. Git is used to track changes to software and can interact with the Github website to save and download code. 

### Windows 
TODO: Add windows instructons

### Mac / Linux
TODO: Add windows / Linux instructions

## Download Code for Workshop (5 min)
Now that you have git installed, we will use git to download the rest of the code for the workshop. The github repository for the workshop is located here:

`https://github.com/jpfeil/Workshop-2018`

### Windows 
TODO: Add instructions for windows

### Mac / Linux
TODO: Add instructions for macs

git clone https://github.com/jpfeil/Workshop-2018


## Install conda (5 min)
You will likely install a lot of software during your research career. Software often requires very specific dependencies and it is difficult to satisfy the dependencies for many different software packages on one machine. Anaconda is a python package manager that makes this process a lot easier. Sometimes software breaks and it can make your operating system non-functional. Installing your software using anaconda mitigates this problem by installing the software in your home directory, so if your software breaks you can just delete the Anaconda directory and start over again. Let's install anaconda now:

### Windows 
TODO: Add instructions 

### Mac /Linux 
TODO: Add instructions

## Install iPython (5 min)
The tools that come out of the box with python are very basic, but there have been several tools recently developed that makes scientific computing with python much more convenient. The next tool I want to share with you is a more interactive form of python called iPython. 

### Windows 
TODO: Add instructions 

### Mac /Linux 
TODO: Add instructions

Python includes a read execute print loop (REPL) tool. You can access this by typing python in the command prompt.

### Windows 
TODO: Add instructions 

### Mac /Linux 
TODO: Add instructions

As you can see it has some very basic interactive features. You can execute a line of python and save state, but it isn't very flexible and can be prone to typos. 

### Write a hello-world function (2.5 min)
Write a hello-world function

`def hello_world():
	print("Hello, world!")
hello_world()
`

IPython is only a slight improvement, but it is convenient for simple tasks. Let's start an instance of ipython and see how it is different than the python REPL.

### Write a hello-world function in ipython (2.5 min)
`def hello_world():
	print("Hello, world!")
hello_world()
`

I think Ipython is helpful because it allows you to use basic command line tools so that you can interact with the filesystem more easily.

### List all of the files in your directory while inside an IPython session
Let's first move to your Workshop-2018 repository.

### Windows 
TODO: Add instructions 

### Mac /Linux 
TODO: Add instructions

ipython will help you with tab completion, so you can hit tab once you start writing out a directory name. Try typing `ls data` in your Ipython session. This is helpful for doing simple calculations while navigating your filesystem.

### Install jupyter notebook (5 min)
The real scientific computing powerhouse is called Jupyter. Jupyter is not specific to python. You can also run R and Julia kernels as well as others. Jupyter notebook is powerful because it allows you to code in an interactive way but you can also preserve your code and notes. This makes your scientific coding reproducible and it reminds you how you obtained those results months after you wrote the code when it is time to publish the results. Let's not install Jupyter using conda.

### Windows 
TODO: Add instructions 

### Mac /Linux 
TODO: Add instructions

While this is downloading you can read up on some Jupyter basics here<https://hub.mybinder.org/user/ipython-ipython-in-depth-qgtzhtmb/notebooks/examples/Notebook/Notebook%20Basics.ipynb>.

### Jupyter basics (5 min) 
Start a jupyter session by typing `jupyter notebook`. This will bring up a filesystem on your browser. Hopefully, you are in your Workshop-2018 repo, so you see that data and notebooks directories. Click on the notebooks file and click the new drop-down menu and select the python kernel. This should bring up an Untitled.ipynb file. Click on Untitled next to the jupyter logo and rename the notebook.

### Documentation (5 min) 
You can use the Markdown language to document your Jupyter notebook. Markdown is a simple language for formatting text. Here are a few commonly used features:
`Headers:
 # - is the largest header
 ## - is a slightly smaller header
 ### - you get the idea...

 Bullet Points
 *
 ...

 Numbered List
 1.
 2. 
`3. 

 Code
 Back tick
 ...
`

Now you can make a todo list for this week using the markdown syntax. Does anyone want to share their TODO list for the week?

### Writing Python Code
By default the cell will execute python code. Each cell can be executing individually, but the state is shared across cells. So, variables you instantiate in one cell will be available in other cells. This is a huge source of bugs, so be careful with how you name variables because you may be modifying a variable unknowingly. Let's write the hello-world function again. To execute the cell you can either press the run button or type shift-enter on your keyboard. Ths should print Hello, world to the jupyter notebook. Jupyter notebooks are very useful for research because you can document your work next to your code. This allows for reproducible results and keeps your research projects moving forward. I highly recommend creating a notebook for each research task you begin. Organizing many jupyter notebooks in a git repo and backing up the notebooks to github is a great way to make progress on your research. It is also easy to share notebooks with collaborators this way. One caveat is that some of the git features will get confused with jupyter notebooks, so do not try to merge notebooks using git.

### Useful scientific libraries for Python
* Numpy
* Pandas 
* Matplotlib
* Seaborn

Use your conda environment to install these libraries (5 min)

### Windows 
TODO: Add instructions 

### Mac /Linux 
TODO: Add instructions

### Numpy (10 min)
Numpy stands for numeric python (TODO: check this), so it is optimized for numeric operations like linear algebra. Python is built on top of the C programming language and can be slow. To overcome this, numpy and other packages optimize routine calculations.

A common way to import numpy is to type:
`
import numpy as np
`

#### Exercise 
We are going to use one of the special features of jupyter notebooks to compare the speed of a linear algebra operation using python and numpy. The special jupyter notebook feature is the timeit magic function. 

Write a function to calculate the product of a scalar and a vector. Create a list of ones of size N and multiple by a scalar of value 42. 

Next pass the list to the numpy.array function to convert the list into a numpy array. You will next use the numpy function numpy.multiply(42, array). 

Finally, put a %%time at the top of each cell and then run the cells individually. Which method is faster?

#### Exercise 2 
Now write a python function to do matrix multiplication. Compare this function to the numpy matmul function.

Numpy is a powerful library of functions and many other scientific libraries are built upon numpy.

### Pandas 
The second library I want to show is called pandas. Pandas provides a dataframe object that is very useful for data analysis. If you are familiar with R, then you have likely interacted with a similar kind of object. You can think of a dataframe as a large table where the rows and columns have labels. The row labels are referred to as the index and the column labels are referred to as columns. Let's create an empty dataframe in the next cell by typing this line:

`
import pandas as pd 

df = pd.DataFrame(index=['a', 'b', 'c'], columns=[1, 2, 3])
`

You can fill in the dataframe by accessing specific rows, columns, or cells. For example, you 
can fill the entire column with a single value by using hard-brackets.

`
df[1] = 'alpha'
``

You can fill in a specific row using 
`
df.loc['b', :] = 'beta'

Likewise, you can fill specific cells using the loc operator

`
df.loc['c', 3] = 'gamma'
`



Download the Treehouse gene expression compendium<https://xena.treehouse.gi.ucsc.edu/download/TreehousePEDv5_unique_hugo_log2_tpm_plus_1.2018-05-09.tsv>.
