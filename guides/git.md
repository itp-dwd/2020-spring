# Git Guide

## Table of Contents

- [Git Guide](#git-guide)
  - [Table of Contents](#table-of-contents)
  - [About](#about)
  - [What is Git?](#what-is-git)
  - [Initialize!](#initialize)
  - [Adding & Committing Changes](#adding--committing-changes)
    - [Check the status](#check-the-status)
    - [Add and commit ALL changes](#add-and-commit-all-changes)
    - [Add single file and commit with a specific message](#add-single-file-and-commit-with-a-specific-message)
    - [Add multiples files and commit with a specific message](#add-multiples-files-and-commit-with-a-specific-message)
  - [Undoing Changes](#undoing-changes)
    - [Show the Commits with `git log`](#show-the-commits-with-git-log)
    - [Resetting](#resetting)
    - [Reverting](#reverting)
  - [Ignoring files from git tracking](#ignoring-files-from-git-tracking)
  - [Branching & Merging](#branching--merging)
    - [Branching](#branching)
      - [Creating a branch](#creating-a-branch)
      - [Switching branches](#switching-branches)
    - [Create and Switch Branches](#create-and-switch-branches)
    - [Merging](#merging)
- [What is Github?](#what-is-github)
  - [GitHub Desktop](#github-desktop)
  - [SSH keys for Git Authentication/Authorization](#ssh-keys-for-git-authenticationauthorization)
  - [Connecting to a remote repository](#connecting-to-a-remote-repository)
  - [Cloning a remote repository](#cloning-a-remote-repository)
  - [Forking an open source project](#forking-an-open-source-project)
  - [Pull requests and contributing](#pull-requests-and-contributing)
- [Quickstart](#quickstart)
  - [Debugging Mistakes with Git](#debugging-mistakes-with-git)
  - [References](#references)

## About 

The best thing you can do for yourself on your developer journey is to use version control and get into the good practice of tracking your project evolution with a version control system. At the time of this writing (and quite likely into the future) we use `git` to do version control.

Git provides many benefits, some of which are outlined here in [Git Centric Workflows](https://www.swyx.io/writing/netlify-git-centric/) (ignore all the references to Netlify and focus on the notes on git).

This guide is about introducing concepts and syntax in git.

## What is Git?

**Git is a software** that allows you to do version control. Like other softwares, the git software is something that you download (or is natively installed on your computer) and can be accessed either via the command line or using a desktop GUI.

You can think of git as a system that allows you to drop "breadcrumbs" along the process of developing a project so that you can:

1. track how your project develops (e.g. when you add new files, make changes to those files, add new features, etc) and
2. go *back in time* in case you break something or want to return to a previous state of your project or retrieve the previous state of a file within your project history.

In this way, git is kind of like a time machine ✨ -- this is what we mean by **version control**: we're tracking the lifetime (the versions) of files as they change as your projects develop.


## Initialize!

```sh
$ cd /path/to/your/project
$ git init
```

## Adding & Committing Changes

Most of the time you will be adding and committing changes with git. The following commands and the combinations will become part of your brain and muscle memory!

### Check the status
> `git status`
Check the status of the files that have been added or have not yet been added to git's tracking system:

```sh
$ git status
```

### Add and commit ALL changes 
> `git add . && git commit -m "adds all changes"` 

```sh
$ git add .
$ git commit -m "adds all changes to all files"
```

### Add single file and commit with a specific message
> `git add index.html && git commit -m "updates title in index.html"`

```sh
$ git add index.html
$ git commit -m "updates title in index.html"
```

### Add multiples files and commit with a specific message
> `git add index.html main.css && git commit -m "updates title in index.html"`

```sh
$ git add index.html css/main.css
$ git commit -m "updates index with new refernce to main.css"
```

## Undoing Changes


More details about the differences and methods for [Resetting or Reverting changes in git](https://www.atlassian.com/git/tutorials/undoing-changes/git-revert) can be seen in the blog post link.

### Show the Commits with `git log`
> `git log`

The `git log` command shows the past commits and is useful if you need to get the commit id number so that you can revert back to that ID.

```sh
$ git log
```

In your console you'll see:

```sh
commit f7bbdc53a033d412c522dc0609874a696ba0fb8e (HEAD -> master, origin/master)
Author: yourGithubHandle 
Date:   Fri Jan 24 17:56:02 2020 -0500

    adds content to foundations

commit 3418c5ce47cf047025b38be770834254eb11af46
Author: yourGithubHandle 
Date:   Fri Jan 24 17:53:28 2020 -0500

    adds toc
```


### Resetting

There are a number of ways to reset or go back to a different version of a file in git. The only way to get a handle of handling resetting and getting older versions of files is to experiment and try these features out.

**Option 1**

See: [Git Checkout Atlassian tutorial](https://www.atlassian.com/git/tutorials/undoing-changes)

```sh
$ git checkout
```

**Option 2**

See: [Git Reset Atlassian tutorial](https://www.atlassian.com/git/tutorials/undoing-changes/git-reset)

```sh
$ git reset
```


### Reverting

**Option 1**: Revert back to the last Commit
```sh
$ git revert HEAD
```

**Option 2**: Revert to a specified commit

```sh
$ git revert <commit id number>
```

e.g. `git revert 3602d8815dbfa78cd37cd4d189552764b5e96c58`


## Ignoring files from git tracking

You can ignore files in git by adding a file to your project folder named `.gitignore`. 

Within `.gitignore` it is common to add:

```txt
node_modules/*
.DS_Store

# any secret files or folders 
.env
private/*

# big files you don't want to be tracked in git
my200mbImageFile.tiff
```

## Branching & Merging

Along with **tracking file changes**, git also offers up other functionality that help make it easier to develop projects (often times code, but can be other things too). One of these key offerings is a concept called **branching**. 

With **branching** in git, say good bye to crazy file and experimental feature testing gymnastics like "myProject-final-1", "myProject-final-final", "myProject-version-with-rainbows" etc. Git provides you with ability to create **branches** or other versions of your project without needing to duplicate your project or create experimental files and so on. 

The idea with branching is that you can create different versions of your project (the branches) then, if you want to or if it is relevant, you can **merge** those versions or experiments into the project. In professional software development, where many developers are working on the same repository, developers will work on **feature branches** and then merge to `master` once the feature is complete and tested.

### Branching

#### Creating a branch

Create a new branch by using `git branch <name of branch>`

```sh
$ (master): git branch new-background-branch
```
* NOTE: the `(<branchName>):` before the `git` command is to indicate which branch you're currently in. DO NOT type in `(master):`.

#### Switching branches

Switch branches by using `git checkout <name of branch>`

```sh
$ (master): git checkout new-background-branch
$ (new-background-branch):
```
* NOTE: the `(<branchName>):` before the `git` command is to indicate which branch you're currently in. DO NOT type in `(master):`.

### Create and Switch Branches

```
$ (master) git checkout -b new-title-branch
$ (new-title-branch):
```

* NOTE: the `(<branchName>):` before the `git` command is to indicate which branch you're currently in. DO NOT type in `(master):`.

### Merging

To merge a branch into another branch, you would first:
1. `git checkout` the branch you want your changes **to come into** then...
2. `git merge <the name of branch whose features you want to get>`
   
For example here we are saying, "I want to get the new updates from the `new-background-branch` and merge them into the `master` branch." In the example below the features from the `new-background-branch` will be merged into the `master` branch.

```sh
$ (master): git merge new-background-branch
```

***
***
***

# What is Github?

Github is a service that allows you to host your git version controlled projects. The general idea is to motivate open software, knowledge sharing, and collaboration.

Github is a platform where you can develop projects -- software or otherwise -- with others.

## GitHub Desktop

[GitHub Desktop](https://desktop.github.com/) is an application that provides you with a GUI for interacting with git and GitHub. It allows you to run git commands outside of the command line, and synchronize your changes with GitHub. It is recommended that you get comfortable using git from the command line, as this is the most common way to use it. However, if you are having issues synching your local repositories with your remote repositories, GitHub Desktop can help.

## SSH keys for Git Authentication/Authorization

If you want to connect to Github from your local repositories, then you'll need to set up SSH keys that allow you to authenticate from the terminal/commandline and push or pull changes from Github to your local machine.

See: [Adding SSH Keys to your Github Account to connect your terminal](https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

## Connecting to a remote repository

**Connect your remote repo**: Send your local repo to the place you want it to go - you need permissions of course
```sh
$ (master): git remote add origin https://github.com/yourUserName/repoName.git

```

**Check your remote repo**: Check if you have a remote repo attached to your git repo
```sh
# check which remote you're working on
$ (master): git remote -v
```

**Push your changes to remote**: Send up your changes to your remote repository
```sh
$ (master): git push -u origin master
```

## Cloning a remote repository

You can clone a git repo into a local directory by doing the following: 
```sh
$ git clone https://github.com/joeyklee/rainbow-gif-maker.git
```

## Forking an open source project

TBD


## Pull requests and contributing

TBD


***
***
***

# Quickstart

Adapted from [dwd-spring-2018](https://itp.nyu.edu/~sve204/dwd_spring2018/git.html).

Git is a versioning system. GitHub is popular public site for hosting git repositories. To add our code to a git repository, in our working folder we run the following one time from the command line:

```sh
git init
git add [FILES TO ADD TO GIT]
git commit -m "[COMMIT MESSAGE]"
git remote add -u origin [REMOTE GITHUB REPO URL]
git push origin master
```

This creates a __local__ git repository.

Note that the [FILES TO ADD TO GIT] can be a list, i.e. `app.js README.md`, or a directory, i.e. `src`, or all of the files in your root directory. i.e. `.`.
				
then when we are ready to edit and make changes and save them we use the following:
```sh
git add .
git commit -m "[COMMIT MESSAGE]"
```

How do you write a good [COMMIT MESSAGE]? See [How to Write a Git Commit Message](https://chris.beams.io/posts/git-commit/). 

to push our new changes to our __remote__ repository on GitHub, we run the following
```
git push origin master
```

If we want to pull a local version of our repo to different place, i.e. a server on a hosting service, or we want a local version of a repo we've found on GitHub, run the following command

```sh
git clone [REMOTE GITHUB REPO]
```
				
Any time we have new changes to we can pull them down with

```sh
git pull origin master
```
				
One handy feature of git is to have it ignore certain files and directories that you don't want included in a repo. To use this, simply create and add a file called `.gitignore` to your repository and in the file list the files and directories you don't want included. This is especially important when using node config files. Here is a sample .gitignore file:

```
.DS_Store
node_modules/
config.js
```

## Debugging Mistakes with Git

For all the wonders of git, it can honestly sometimes create A LOT of headaches. There will be times when you'll need to debug things like **merge conflicts** or other issues and you won't know what to do or where to go. You'll do a lot of googling for answers and asking people for help. You can start here for some tips.

* [Oh Shit Git](https://ohshitgit.com/)

## References

* [Coding Train - Git and GitHub for Poets](https://www.youtube.com/playlist?list=PLRqwX-V7Uu6ZF9C0YMKuns9sLDzK6zoiV)
* [Getting Started With Git](https://www.taniarascia.com/getting-started-with-git/)
* [The Complete Git Guide](https://flaviocopes.com/git/)
* [Git Workflow to manage work on Multiple Branches](https://flaviocopes.com/git-workflow/)