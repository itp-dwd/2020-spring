# Assignment 1: Internet Art - The Materiality of the Web

## Briefing

![Assignment 1 demo - net art with rainbows and gif](/assets/assignment-01__demo.gif)

Your task this week is to code a "simple" website using HTML and CSS. The goal of this assignment is to begin your practice of the web development and deployment process. 

Your focus should be to get into the habit and practice of integrating git tracking into your workflow and exploring as much of the features of HTML as possible, displaying your understanding of the DOM tree and creative uses of the CSS knowledge you have so far. 

The mantra this week is: 

```txt
code → track → sync → deploy (repeat)
```

Please refer to the [Required Reading](#required-reading) for relevant information as well as to the [Helpful Tips and References](#helpful-tips--references)  and [Supplemental References](#supplementary-references) for additional tips.

## Required Reading
* [HTML Guide](guides/../guides/html-guide.md)
  * Specifically:
    * [Introduction to the DOM](https://www.taniarascia.com/introduction-to-the-dom/)
    * [Understanding the DOM Tree](https://www.taniarascia.com/understanding-the-dom-tree-and-nodes/)


## Requirements

Your assignment consists of two parts:
1. Setup and,
2. Development

### Part 1: Setup

#### Requirement 1.1: Downloads and Accounts

Setting up your development environment now will be key to your experience for the rest of the semester. Part of of your assignment is to ensure that you've got your development environment in good shape so you can develop like a pro. 

Ensure that you've setup the software listed in:
* ↳ [Developer Setup Guide](../guides/developer-setup-guide.md)

**Optional**:
* *VSCode*: [Customize your VSCode](https://code.visualstudio.com/docs/introvideos/configure)
* *Commandline*: Customize your command line. Warning: This can be a black hole for your time. For example, Cassie uses [iTerm2](https://www.iterm2.com/) (an alternative to Terminal on MacOS), [Oh-my-zsh](https://ohmyz.sh/) (package manager for zsh), and [Starship](https://starship.rs/) (customizes your command prompt).

#### Requirement 1.2: Linking Git & Github via the Commandline

In this first class, we introduced Github desktop because it is provides an interface to git with zero configuration. It is handy for debugging and having visual feedback for what your git tracking is up to, however, as a developer it is important to get into the practice using the commandline because it is the main tool for just about everything from downloading software, setting up projects, deploying changes to remote servers, etc. Getting comfortable with git via the commandline will not only increase your development speed (as opposed to having to click around the Github desktop GUI), but also serve you well as you start to take advantage of the ways that git/github are integrated into devOps processes in the world of web development.

For this requirement 1.2, you will be creating a link between your git and Github using SSH keys to allow Github to authenticate your local machine when trying to "push" to your remote Github repositories. To do so, please follow the instructions provided here:

* ↳ [Generate an ssh key and add it to your GitHub account](https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent).
   

You'll know that this works when you are able to the following command and see those changes reflected in your remote Github repository.

```sh
# should return nothing so far
$ git remote -v


# Then you can add a remote repo assuming you've created a Github repo
$ git remote add origin https://github.com/YourUserName/CoolNetArtProject
# Then you can push your changes from your local repo to the remote
$ git push origin
```


### Part 2: Net Art

Creating, from scratch, a simple web page using only HTML, CSS, and media assets (images, videos, gifs, fonts, etc.). No JavaScript! You could make a page about your beloved pet, or maybe a work of hypertext art, fiction, or poetry. Try looking at [Rhizome's Artbase](https://rhizome.org/art/artbase/), specifically [Collection: Hypertext](https://rhizome.org/art/artbase/collections/collection-hypertext/) for inspiration.

#### Requirement 2.1: Developing like a pro
* A web application deployed to the web following best practices.
  * Your code and changes to your code must be well tracked using git
  * Your code must exist as a Github repository
  * You must `add`, `commit`, and `push` changes from your local development environment to your remote Github repository. (note: see requirement 1.2 above)


#### Requirement 2.2: An awesome README.md
* You must have a `README.md` that explains:
  * how to set up and run your application.
  * how you built your HTML page
  * inspiration, process documentation, struggles, references, and questions, like your ITP blog
  * and how you deployed your work to [Glitch.com](https://glitch.com).
* You may use this [README template](/templates/readme-template.md) to structure your README documentation and blog post
* See the [Markdown Guide](../guides/markdown-guide.md) or syntax help.

Some examples of nice readme:
* [p5.js Readme](https://github.com/processing/p5.js)
* [ml5.js Readme](https://github.com/ml5js/ml5-library)
* [p5 serial](https://github.com/p5-serial/p5.serialport)
* [Opentype js](https://github.com/opentypejs/opentype.js/blob/master/README.md)

#### Requirement 2.3: Deployed publicly to Glitch
* Your application must be publicly accessible on [Glitch.com](https://glitch.com). For more information on deploying to glitch via a remote Github repo, see: [Glitch Guide](../guides/glitch.md).

## Submission

**Details:**
* Due Date: week 2 - Feb 3
* Your assignment must be turned in BEFORE midnight on Sunday, the day before class, Feb 2.

**📨All Assignments should be submitted to your respective section:**
* Section 1:
  * [Joey's Section - Assignment Submission Form](https://forms.gle/GkLsRM581kfyHg6W6)
* Section 2:
  * [Cassie's Section - Assignment Submission Form](https://forms.gle/pzxHjZtq1iP5WAyv9)


## Helpful Tips & References:

* [Your First Website Guide](../guides/your-first-website-guide.md)
* [CSS Guide](../guides/css-guide.md)
* [Commandline Guide](../guides/commandline.md)
* [Git Guide](../guides/git.md)
* [Quick Web Server Guide](../guides/quick-web-servers.md)
* [Glitch Guide](../guides/glitch.md)

## Supplementary References

* [CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* [CSS Keyframe Animations](https://www.w3schools.com/css/css3_animations.asp)