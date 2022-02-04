<h1 align="center"> Git Tutorial </h1>
<h3 align="center"> Created by Christopher Linscott </h3>
<p align="center"> A guide to setting up and using a Git repository in correspondence with Github.<p>

## Table Of Contents:

1. [Introduction](#introduction)
    * [What is a Git Repository?](#what-is-a-git-repository)
    * [Git's "Assembly Line"](#gits-assembly-line)
2. [Getting Started](#getting-started)
3. Branching
4. Topic 4
5. References


# Introduction

Before we get started, having a bit of knowledge of what a Git repository is and the "assembly line" of the 4 possible areas where you code could currently be (from Git's perspective) can be quite helpful before you start this tutorial.

## What is a Git repository?

A Git repository is simply a folder that contains the *changes* you make to your project, whether you __add, change, delete, or rename__ a file.

> "Deleting your folder is deleting your project's history..." *- GitKraken*

You won't see it since it's stored as a hidden folder, but if you're curious:

<img name="image" src="images/git-folder.png" width = 200/>

## Git's "Assembly Line"

### The way I think about it is, your code can be in one of 4 stages:

* Working Tree
    * Your home base: files that have been added, changed, etc, but that aren't ready to be added to the codebase just yet.
        * Maybe a feature you're still fixing a bug on, or a file you don't want to be seen by the public.
* Staging Area
    * Control center: add what you *want* to commit, keep what you don't in the working tree.
* Local Repository
    * 
* Remote Github Repository
    * Your "production", where the code is now open to the world or whatever team you're working on.

### Code will flow from the working tree to the remote github repository.

# Getting Started
### To begin, there are mainly 2 ways to initalize or start a Git repository.

1. Creating a Github repository on your Github account, and cloning it onto your local machine. (__*recommended*__)
2. Initalizing a Git repository on your local machine, creating a Github repository, and setting the origin (or where you push the code) to be the Github repository's URL.
    * Given, this is a Git __Command Line__ Tutorial, my tutorial will cover this way.

## Setting Up The Git Repository

First, find and/or create a folder you want to call this project's home. 

I will be creating a folder inside of my COMP 390 folder named: `git-test`.

Next, go into your terminal and navigate to this folder by grabbing the path and typing in the following path: `cd {path_name}`

    cd /Users/lchris/Desktop/Coding/schoolprojects/comp390/git-test
> Note: If you have VSCode and you open VSCode with the folder you create, the terminal will be adjusted to the folder's location.

Great! Now, simply type in the following command:

    git init

This should return:

    Initialized empty Git repository in /Users/lchris/Desktop/Coding/schoolprojects/comp390/git-test/.git/

and will initalize the Git repository inside of the folder, which can be seen as shown [above](#what-is-a-git-repository) if you have your hidden files showing.

Now, feel free to add any small files (.txt) to get your project started and confirm it's all working for the later steps.
Here's some free code to copy (and I'll be making a random file two_sum.py to populate my git repo).

```python
/COMP390/git-test/two_sum.py

def two_sum(arr, target):
    sum_dict = {} # Returns index of number
    for index, num in enumerate(arr):
        curr_complement = target - num
        if curr_complement in sum_dict:
            return [sum_dict[curr_complement], index]
        sum_dict[num] = index
    return [-1, -1] # Not found
```

## Working Up The Tree

Great, you should now have a repository with a folder containing some files.
Now, our code is currently in stage 1, in the working tree.

To say to Git 'our code is ready to be set in stone (Github's history that is)',
we do the following:

```git add .``` OR ```git add {file}```

Ex: ```git add two_sum.py```

Great! Now, you're code is in the staging area.

## The Staging Area

So, your code is in the staging area now. You have two options:
- If you like the code and you want to make it set in history, *commit* it.

To commit, do the following command:
> NOTE: the title is only required, omit the second -m to exclude a description.

```git commit -m "{title_of_commit}" -m "{description_of_commit}"```

Ex: ```git commit -m "Added twosum.py" -m "Added a file which can compute the indices of an integer array, where the integers located at this indices adds up to a target value."```

- If you don't like how it is so far, you can *restore* it from the staging area by the following command.

```git restore --staged```

Upon commiting, you should see a similar message:

<img name="image" src="images/git-commit.png" width = 200/>

Assuming you're comitting, we've now hit the 3rd stage of Git's assembly line: the local repository.

## The Local Repository

We're almost there! It's set in stone (or history) on *our local machine*, but not on Github, or where it could be accessed and pulled by someone else.

Now, we need to set up a repository on Github for use. Navigate to [Github](github.com) and create an account if you don't already have one.




# TODO: BELOW (After Initalizing Git Repo with Github ...)


> Note: The commands shown below will make more sense, given the knowledge of [Git's 4 data stores](#gits-assembly-line).

All commands will normally be prepending with word `git`.



# Branching

# Merging/Rebasing

# References
Special thanks to these videos/articles
for contributing the knowledge to make this project possible:
* [GitKraken](https://www.gitkraken.com/learn/git/tutorials/what-is-a-git-repository)