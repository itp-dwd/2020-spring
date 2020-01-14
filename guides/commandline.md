# An introduction to the command line

You're probably familiar with interacting with you computer using its Graphical User Interface, or GUI. If you want to open an application, say Firefox, you might find a graphical icon that represents the browser, use your mouse to hover over it, and double click on the icon to open the application. This is, in fact, how you do most of the actions on your computer, interacting with icons, or dropdown menus, or other visual elements.

![Screenshot of macOS terminal window](/assets/commandline-01.png)


## Directories
You can, however, interface with your computer only using text. You write commands using text, and the computer will execute those commands. Sometimes it writes text back at you, or it might open an application, or produce a sound—it will do whatever you told it to do. You can write these commands to your computer using the *command line*, also known as the command line interface, or CLI.

## Why use the command line?

You may find the command line difficult or tedious to use. However, it is an essential tool to writing software, and important that you start to get comfortable using it in the context of this class. It enables you to do new things with your computer, that aren't even possible just using the GUI! It also gives you the power to break your computer in major ways—with great power comes great responsibility, see [Don't blindly run commands that you find on the Internet](dont-blindly-run-commands-that-you-find-on-the-internet).

## First Steps

Open an application on your computer called "Terminal". When it opens, you'll get a prompt which looks something like this:
```sh
Cassie-Tarakajians-Macbook:~ ctarakajian$
```
Followed by a cursor, blinking, ready for input. Let's break down what all of this means.
* `Cassie-Tarakajians-Macbook` - This is the name of the computer that you have a terminal session open to. In this case, it is the name of my computer. It may seem obvious, like, "duh, if I've opened Terminal on my computer, I'm trying to connect to my computer." However, through the Terminal interface, you can connect to any computer connected to your network or the Internet (provided you have the correct credentials). We'll get to that later in this class.
* `~` - This is where you are (which folder you have open) on your computer. `~` is shorthand for your "home" directory. More on this in a moment
* `ctarakajian` - This is the account you are running commands as, which is the account you're logged in as on your computer. It is possible to switch accounts, but most of the time you will not need to.
* `$` - This is a symbol that represents the prompt. It tells us that our machine is ready and awaiting commands.

Let's input our first command. From now on, I'm going to shorten the prompt to just `$`, which you don't need to type when inputting commands. Type
```sh
$ pwd
```
and hit enter. `pwd` stands for "print working directory" and it tells us where we are. You should get something like
```sh
/Users/ctarakajian
```
Since I'm logged in as `ctarakajian`, this makes sense. `~` stands for the home directory for your account. `/Users/ctarakajian` is the *path* to where you are currently located—more on paths a little later. 

Let's try some more commands! Try
```sh
$ ls
```
and hit enter. `ls` is short for "list", and tells you all of the files that are in a directory. You'll see something like
```sh
Applications        Library         Pictures
Desktop             Movies          Public
Downloads           Music           
```

## Anatomy of a command

So far, we've used two commands, `pwd` and `ls`. Commands often have arguments which specify how the command should run. For example, try running
```sh
$ mkdir dwd
```
`mkdir` is short for "make directory" and creates a folder with the name specified by the argument. In this case, I named it "dwd" (short for our class, dynamic web development). Now if we enter the command
```sh
$ ls
```
we should see `dwd` in the list of all files within the current directory. You can move to that directory by entering 
```sh
$ cd dwd
```
We can verify that we've changed location in a few ways. Your command prompt has probably changed to
```sh
Cassie-Tarakajians-Macbook:dwd ctarakajian$
```
or, you could enter
```sh
$ pwd
```
and you should see
```sh
/Users/ctarakajian/dwd
```

Some commands also take flags as arguments, which change the behavior of the command and are prepended with a `-`. For example, if you're still in the `dwd` directory, type
```sh
$ ls
```
Because we just created this directory, there's nothing in it, and therefore `ls` will return nothing. Now try entering
```sh
$ ls -a
```
You should see in response
```sh
.	    ..
```
which is a little mysterious. What does the `-a` flag do? It includes all items in the directory that begin with a `.`, which are sometimes referred to as dotfiles. What are these `.` files and why are they in the empty folder I just created? They are special files that every directory has. `.` is an alias for the current directory (in our case, `/Users/ctarakajian/dwd`), and `..` is an alias for the parent directory (in our case, `/Users/ctarakajian`). We can test this out by running
```sh
$ cd .
$ pwd
```
which will return
```sh
/Users/ctarakajian/dwd
```

but then try
```sh
$ cd ..
$ pwd
```
which will return
```sh
/Users/ctarakajian
```
I'll get more into why `.` and `..` are useful in the next section about paths.

## Paths: how do they work?
When you interact with your computer using the GUI, you use windows, icons, navigations, and dropdown menus to navigate around your computer. But on the command line, you don't have access to these things, all you have is your computer's file system. Everything is either a file or a folder. When we write software, we're creating a collection of files that all belong to a project (that share a root folder). Using paths is essential to getting around your computer from the command line interface.

When we open a new terminal session, we land in `~`, or `/Users/catarakajian`. If we enter
```sh
$ cd ../..
```
this takes us two levels up—first to the parent directory of the `ctarakajian` folder, and then to the parent directory of the `Users` folder, which is `/`. You can try `pwd` to confirm this. Now, if we wanted to navigate to the `dwd` folder we created earlier, we could enter any of the following commands
1. 
```sh
$ cd ~/dwd
```
2. 
```sh
$ cd /Users/ctarakajian/dwd
```
3. 
```sh
$ cd Users/ctarakajian/dwd
```
4. 
```sh
$ cd ./Users/ctarakajian/dwd
```
5. 
```sh
$ cd ./Users/../Users/ctarakajian/dwd
```
what happens if you try to enter (3) or (4) again? You see an error right? `-bash: cd: Users/ctarakajian/dwd: No such file or directory`. Why is that? (3) and (4) are *relative paths*, which mean they depend on the directory you are currently in. So when you run (3) or (4) again, you're telling your computer
6. 
```sh
$ cd /Users/ctarakajian/dwd/Users/ctarakajian/dwd
```
which doesn't exist. (2) and (6) are *absolute paths*, which do not depend on the directory you're currently in, and always begin with a `/`.

(5) is kind of silly but it just demonstrates how you can chain together `.`, `..` and folders to create useful paths.


## Common commands

| Command      | Description                                | Example      |
| ------------ | -------------------------------------------|------------- |
| `pwd`        | Returns the path to the current directory. | `$ pwd`      |
| `ls`         | Lists the contents of the current directory. | `$ ls`     |
| `ls <path/to/directory>` | Lists the contents of the given directory. | `$ ls /Users/ctarakajian` |
| `ls -1` | list all files in a the current directory separated by a linebreak | `$ ls -1` |
| `ls -1a` | list all files in the current directory separated by a linebreak including the hidden files | `$ ls -1a` |
| `mkdir <path/to/directory>` | Creates a directory with a given path. | `$ mkdir /Users/ctarakajian/dwd` |
| `cat <path/to/file>` | Prints the contents of a file. If multiple files are given, the output is concatenated together. | `$ cat ~/dwd/README.md` |
| `cp <src/path> <dest/path>` | Copies the contents of a file to a new one with a different name. | `$ cp ~/one.js ~/two.js` |

## DON'T BLINDLY RUN COMMANDS THAT YOU FIND ON THE INTERNET

Don't blindly copy and paste commands into the terminal that you found on Stack Overflow, especially ones that contain `sudo` or `rm`. This is a great way to mess up your computer! Take a moment to try to understand what is happening, or why someone is suggesting it, or look at a few different suggestions before choosing one.

## Network


## Permissions


## Further Reading

The command line is extremely powerful, and this is just an introduction! There's so much more to learn and explore. It's personally one of my favorite tools, as I feel like it gives me insight into how computers work at a lower level, and makes me feel like a hacker.

* Cheat Sheet: https://www.git-tower.com/blog/command-line-cheat-sheet/
