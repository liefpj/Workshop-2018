# Day 2: Developing your own projects

The first part of this workshop was to introduce you to useful tools for the field. Today, I want to show you some basic techniques for getting your project off the ground.

### Pycharm 
There are many IDE's for python, but I have found that Pycharm is the best. You are welcome to use whatever you like, but Pycharm is what I recommend you use. One of the downsides for Pycharm is that you have to pay for it... However, if you are a student, then you can apply for a student membership which is fee. Hopefully, you have already installed pycharm.

Unlike other IDE's, when you open a pycharm session you can only work on one project at a time. You can open several sessions, but don't mix files from different sessions because pycharm will try to integrate them. Basically, when you open a pycharm window, try to work on only one project.

To start a new project, you simply click on the File menu and select open. This will open a file browser and then you will select the directory your project is in.

Pycharm has some nice features like tab completion, style suggestions, syntax error notifications, a built in terminal, and a debugger.

### Argparse 
Most bioinformatics software is used using the command line. The command-line gives you direct access to your computer which gives you flexibility and power. Programs that do just one thing are not very interesting, so we will also need a way to modify your programs at runtime, so we can do more than one interesting thing. To accomplish this, we will use the python Argparse library. The argparse library is very convenient and once you become familiar with using the library you will find that you can copy and paste argeparse code from old programs into your new programs. 

### Exercise:
Use the run.py script as a starting point for your program. Write a function called echo that prints whatever you pass to it. Then add a command line argument called --echo that takes from the command line a string and passes it to your echo function to print it out.

#### Setting the source directory 
Once you start making more complex programs, you will need to become familiar with loading your own modules. Loading modules in python is straight-forward because you just have to add an empty file called __init__.py in the directory with your modules. Then, you need to add that directory to your python path. This can be complicated, but pycharm makes it easier to develop. Go to file -> settings -> project structure and then set the rosalind source directory as your Sources by clicking on the rosalind directory and the mark as: Source button at the top of the window. Now your python path should be modified appropriately to load a module.

### Exercise:
A general workflow that I have experienced is that you will write functions in your main script (run.py) but then you want to add more features. So, to make less clutter in your run.py script, you will cut functions out of run.py and place them in a module. I like to make a module called util.py in the library directory for basic functions like echo. So, create a module called util.py, add your echo function to this module, and finally import this function in run.py. Make sure you get the same results. 

### Rosalind 
In case you don't have enough problems to solve in your research, you can always practice bioinformatic exercises using the Rosalind website. This is a great way to learn new algorithms or programming languages. Basically, Rosalind provides a series of questions with increasing difficulty. Each problem gives background for the biology and the computer science. It also provides a training data set with solution before allowing you to download the test data. Be aware that you only have 5 minutes to upload your solution to the problem.

### Exercise:
We will make your program capable of solving all of the rosalind problems...eventually. We will use the subprogram feature of the argparse tool to determin which problem to solve. Name the subprogram after the name of the first rosalind problem. Then, create an argparse command-line flag to take the input from the rosalind website and a name for the output. You can allow the default output file name to be "output.tsv".

Tip: 
It's a good idea to keep your programs DRY (don't repeat yourself?). When you add a function to util.py for example, try to use the same function for other rosalind problems.

### Git

Make a branch for each problem and then rebase the problem onto the master branch. Make an issue for each rosalind problem. And then make a pull request for each problem. 

### Docker

Create a docker container for your rosalind solving machine. Push the container to your Dockerhub account. Now use your partner's version of the rosalind solving machine to solve the next problem. Have a version number for each problem it is capable of solving. If you change the way the program functions, make a major version change, and if there is an important bugfix, create a hotfix version.
