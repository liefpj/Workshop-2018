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
We have already used GitHub to download the source code for the workshop. I recommend you use github for all of your programming tasks. This way your code is secure so it will survive even if you spill diet coke on your laptop. It also makes it easy to distribute your code to collaborators as well as show people what you are working on.

That being said, git is not an easy tool to use and should be used with extreme caution. Since it is entirely a command-line utility it is difficult to know exactly what the commands are doing until you have used the tool for some time and have seen all the possible outcomes. 

Let's open up the git bash on windows and the terminal on your mac machines. The first command you should become familiar with is git status.

Execute: 
git status

This command will list out the branch you are on as well as any changes that you have made to the program. One limitation of github is that you cannot put large files there, so be careful not to add files larger than 10MB to your repo. For example, the cast.csv file is too large for github. So, do not add this file to the repository.

During the course of this workshop, you have made several changes to the notebooks and other files. Use the git diff command to see all of the changes you have made since the last commit was made in this repo.

Once you are happy with the changes you have made, you can add each individual file using the git add command. 

### Exercise:
Go through all of the files you have modified and add them to the repo. 

Example:
`git add <path to file>`

Now that we have bundled all of the changes, we can use the git commit command to make an official commit to our repo. It's good practice to make an informative commit message so you know what is in the commit exactly. Say you want to go back to a previous version. You can use these commit messages to remind you where you left off in the last commit.

### Exercise:
Think of a commit message that describes the work you have done so far.

Example:
`git commit -m <Your commit message>`

The git log command allows you to see the commits that have been entered for a branch.

### Exercise:
Check that your commit was logged successfully by executing the `git log` command

You have been working in my copy of the workshop code, but you will want to save your personal changes ot your own github repo. To do this you will need to make a fork of my Workshop-2018 repo and then add your fork as a remote repo.

### Exercise:
1. Go to the Workshop-2018 repo and click the fork button in the top right side of the page
2. Use the `git remote add <name for fork> <url for your forked repo>`

When you are ready to "save" your changes on github, use the `git push` command to push your changes to the github website. This will save your changes on the master branch.

### Exercise:
Push your changes to your forked repository. 

Example:
`git push <name for fork>` 

### Workflow 
Now I'm going to descibe a workflow you can use to get work done. I have found that this is a nice way to collaborate with others on a project and keep track of progress. The basic idea is to make github issues for each modification to the repo and then make a git branch for each issue. Then, when you are done with your changes and you are ready to merge them with the master branch, you start a pull request that will merge those changes in.

### Exercise:
1. Make a github issue on your fork for the next rosalind problem
2. Make a branch for the next rosalind probem using `git branch <name of branch>` (I recommend using the issue name in the branch name (i.e. issue-2/solve-rosalind-2)
3. Now make your changes to the rosalind directory to solve the second rosalind problem
4. Check your solution using the rosalind website
5. Add, commit, and push your changes to the branch (i.e. `git push issue-2/solve-rosalind-2`)
6. Go to your forked repo on github. You should see a line that says something like "make a pull request for recent changes?" Click that button
7. Review the changes you have made and make sure everything looks alright
8. Go to the bottom of the pull request and click merge code
9. Now on your computer...checkout the master branch using the command `git checkout master`
10. Now your github master branch is farther along than your local branch. To bring these changes to your local machine use the git pull command (i.e. `git pull <name of fork> master) 

### Exercises:
Repeat this process again for the next rosalind problem.


### Docker
One of the issues with distributing software is that an algorithm may behave differently on my computer than on your computer depending on the other libraries you have on your computer. To make life simpler, a lot of smart people developed a tool called Docker. Docker is basically a virtual machine that allows you to ship your code with all of its dependencies. We will learn how to install docker and then we will package your rosalind solving machine in a docker container and then you will have your partner run your code on their machine to show how easy it is to run other people's code when using docker.

#### Windows 
You will need to make a docker account first

Follow the instructions here: 
https://store.docker.com/editions/community/docker-ce-desktop-windows 

Open the PowerShell and run `docker version`
Check that docker is installed correctly by running `docker run hello-world`

#### Mac
Follow the instructions here:
https://store.docker.com/editions/community/docker-ce-desktop-mac

Open the a terminal and run `docker version`
Check that docker is installed correctly by running `docker run hello-world`

### Dockerfile 
The next thing we need to do is make a Dockerfile that packages up your code and creates a docker container. Think of a Dockerfile as a list of instructions for creating a docker container. They function very similarly to bash commands for installing software. Set your version number to the number of problems you have solved. So, the first version shoulse be 0.1.0. If you change the way the program functions, make a major version change, and if there is an important bugfix, create a hotfix version.

Running a docker container is the most difficult part of this. You have to keep in mind that your docker container is like it's own linux computer running inside your computer. So, your docker container does not behave like your computer. You also have to mount your filesystem because the docker container's filesytem is different than your filesystem. To make this easy, just always run your code in your working directory and always mount your working directory as /data in the docker container. For example,

`docker run -it -v $(pwd):/data/ DockerhubName/rosalind:version -h`

The -it makes it an interative session and also terminates the container at the end. The -v stands for volume and it is this command that maps a directory on your filesystem (your working directory) to the docker container filesystem at /data/. If you stick with this then you should be fine.

#### Exercise:
1. Fill out the Dockerfile for your version of the rosalind project
2. Build you container "docker build . -t DockerhubName/rosalind:version"
3. Run your docker container (see note above)
4. Now push the container to your dockerhub account "docker push DockerhubName/rosalind:version"
5. Now pull your partner's docker container and make sure you are getting the same answers to the rosalind problems. "docker pull DockerhubName/rosalind:version"

#### Exercise:
This is a challenge problem. You and your partner are going to implement the next rosalind problem, but you are not going to submit your own solution. In the time it takes to download the data, you will pull your partner's code from dockerhub, run it on the data, and upload their solution to your account. Your partner will do the same thing, but with your code.
