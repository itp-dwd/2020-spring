# Process and Workflow: Beginner Developer

## About

If you're here, you've probably developed interactive "sketches" in p5.js in the web editor, but are now ready to start developing web sites and applications outside of web IDE (interactive development environment). 

This guide is meant to give you a perspective on how we (your instructors) might develop a *simple*, no-frills front end website or web application. 


## Setup

### Prerequisites

First thing's first: make sure you've downloaded and installed the materials outlined here:
* [Developer Setup Guide](developer-setup-guide.md#materials)

Basically, we're looking to make sure you have *at least*:

* an modern text editor
* you know how to open your terminal/commandline
* you have an account on Github.com
* you have an account on Glitch.com

### Create your project folder:

Create a folder for your project. You can do so by navigating to wherever you choose to organize your projects (e.g. `~/Documents`) and then doing:
* `right click` in the `~/Documents` directory > select: "new folder" 
* `right click` on `untitled folder` > select: "rename" > type: `myProject`


Now you'll have a new project called `myProject` in your `~/Documents` folder. It is in this folder where all your project files will live.

```txt
~/Documents/myProject
```

### Minimal scaffold for your structure:

It is helpful to "scaffold" out a structure for your project so you can fill in the code where it is relevant and you can keep your project tidy and consistent.

You may consider adopting a structure like this assuming you will have HTML/CSS/JavaScript:

```txt
/myProject
  index.html
  /js
    index.js
  /css
    main.css
  /assets
    (any images or other assets)
```

To start adding files to your project:
1. **Fire up your text editor** (in this case we're using VS Code)
2. Open your project folder: you can either
   - drag and drop your folder into your VS Code window OR
   - menu: file > select: open > navigate and click on the folder you made in `~/Documents/myProject`
3. Start adding files by:
   - `right click` on the side panel > select: new file > type: e.g. `index.html`
4. Start adding subdirectories by:
   - `right click` on the side panel > select: new folder > type: e.g. `js`


### Start tracking with Git

The best thing you can do for yourself on your developer journey is to use version control and get into the good practice of tracking your project evolution with a version control system. At the time of this writing (and quite likely into the future) we use `git` to do version control.

You can read more about how git works in the [Git Guide](/guides/git.md) but you can think of git as a system that allows you to drop "breadcrumbs" along the process of your project development so that you can:

1. track how your project develops (e.g. when you add new files, make changes to those files, add new features, etc) and
2. go *back in time* in case you break something or want to return to a previous state of your project or retrieve the previous state of a file within your project history.

In order to "drop those breadcrumbs" you'll need to know a few commands, namely you'll need to know how to:
1. `git init`: initialize a git repository -- e.g. initialize the git system tracking changes in your folder
2. `git add .` or `git add index.html`: adding files to the git tracking system
3. `git commit -m "message"`: "committing" those files and any changes with a message indicating what was changed.

For the purpose of this guide, you can do the following now:

```

```

<!-- 

Git is Like, "wow" for a number of reasons namely:

1. your entire project lives in itself: 
   - Git branching: say good bye to crazy file and experimental feature testing gynastics like "myProject-final-1", "myProject-final-final", "myProject-version-with-rainbows" etc. Git provides you with ability to 

 -->
