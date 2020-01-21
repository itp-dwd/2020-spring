# Guide to Glitch

## About

This is a guide to deploying your web sites/web applications to Glitch. 

## Table of Contents

- [Guide to Glitch](#guide-to-glitch)
  - [About](#about)
  - [Table of Contents](#table-of-contents)
  - [Static Websites and web applications with no server](#static-websites-and-web-applications-with-no-server)
    - [Option 1: via Github](#option-1-via-github)
    - [Option 2: via the VS Code Integration](#option-2-via-the-vs-code-integration)
    - [Option 3: coding directly in the interface (not recommended)](#option-3-coding-directly-in-the-interface-not-recommended)
  - [Deploying full stack applications](#deploying-full-stack-applications)
    - [Package.json & `.env`](#packagejson--env)
    - [Databases & Options](#databases--options)

## Static Websites and web applications with no server

Glitch will serve your static HTML sites out of the box. No need to program a server or anything. There are a few options for getting a webpage up onto glitch, in order of best practice in our humble opinion:

### Option 1: via Github

The best practice to serving up your web site to Glitch is to use the Github integration. Using this option, your workflow might look something like this:

1. (local): create a folder, e.g. "rainbow-project"
2. (local): initialize git
3. (local): start adding files and making changes
4. (local): track your changes by adding and committing your changes
5. (remote): create a Github repo with the same name as the one on your local machine, e.g. "rainbow-project"
6. (local → remote): connect your local repo to the Github repo using the Github desktop tool or via the commandline by "setting the remote url"
7. (local → remote): push your changes from local to remote
8. (remote → remote): `Create a new Project > Clone from Github`
  
If you make changes to your project:

1. (local): add and commit your changes
2. (local → remote): push your changes from your local repo to your Github repo
3. (remote → remote): `menu > tools > git, import and export > import from github`

### Option 2: via the VS Code Integration

↳ [Glitch for VS Code!](https://glitch.com/culture/announcing-glitch-for-visual-studio-code/)

### Option 3: coding directly in the interface (not recommended)


## Deploying full stack applications

### Package.json & `.env`

### Databases & Options