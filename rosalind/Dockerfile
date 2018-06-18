FROM ubuntu:16.04

MAINTAINER Your Name, Email

# Update and install required software
RUN apt-get update --fix-missing \
    && apt-get install -y build-essential <what software do you need?> \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

COPY <copy your project to /opt in your container>

ENV ROSALIND_SRC=<save the path to your code in an environment variable>

# Set the working directory. It is common practice to set 
# the working directory to /data
WORKDIR <set working directory>

# Now you need to figure out what the command should 
# be when you run your container. This is usually 
# the run.py script.
ENTRYPOINT <list of command line arguments>

# This is the default command for your docker container.
# People usually set this to the help (-h) command
CMD <list of command line arguments>
