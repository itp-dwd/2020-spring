# Git

Adapted from [dwd-spring-2018](https://itp.nyu.edu/~sve204/dwd_spring2018/git.html).

Git is a versioning system. GitHub is popular public site for hosting git repositories. To add our code to a git repository, in our working folder we run the following one time from the command line:

```sh
git init
git add [FILES TO ADD TO GIT]
git commit -m "[COMMIT MESSAGE]"
git remote add -u origin [REMOTE GITHUB REPO]
git push origin master
```
				
then when we are ready to edit and make changes and save them we use the following:
```sh
git commit -m "[MESSAGE]"
git push origin master
```
				
That will ensure that we have a stored copy of the previous versions of the files along with our new changes on GitHub and in our local GIT repos.

If we want our repo to be used elsewhere, perhaps on our server, we do the following:

```sh
git clone [REMOTE GITHUB REPO]
```
				
Any time we have new changes to we can pull them down with

```sh
git pull origin master
```
				
One handy feature of git is to have it ignore certain files and directories that you don't want included in a repo. To use this, simply create and add a file called .gitignore to your repository and in the file list the files and directories you don't want included. This is especially important when using node config files. Here is a sample .gitignore file:

```
.DS_Store
node_modules/
config.js
```
