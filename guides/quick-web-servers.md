# Quick Web Servers

## About

When running client side web applications, often you will need to create your own simple web server to serve your HTML, CSS, and JavaScript. This guide outlines a few options for creating a simple web server.

## Table of Contents

- [Quick Web Servers](#quick-web-servers)
  - [About](#about)
  - [Table of Contents](#table-of-contents)
  - [Stopping any terminal/commandline process:](#stopping-any-terminalcommandline-process)
  - [Option 1: Python -- Simple Web Server](#option-1-python----simple-web-server)
    - [Step 1: change directories and run a "simple" web server:](#step-1-change-directories-and-run-a-%22simple%22-web-server)
    - [Step 2: see your files](#step-2-see-your-files)
  - [Option 2: Node.js -- http-server module](#option-2-nodejs----http-server-module)
    - [Step 1: install the `http-server` module](#step-1-install-the-http-server-module)
    - [Step 2: change directories and run a "http-server"](#step-2-change-directories-and-run-a-%22http-server%22)
  - [Option 3: Node.js -- live-server package](#option-3-nodejs----live-server-package)
    - [Step 1: install the "live-server" module](#step-1-install-the-%22live-server%22-module)
    - [Step 2: change directories and run a "live-server"](#step-2-change-directories-and-run-a-%22live-server%22)


## Stopping any terminal/commandline process:

1. go to your terminal window
2. press: `control` + `c`

## Option 1: Python -- Simple Web Server

Most computers have python installed by default. As this is the case, you can quickly and easily serve up your project specific files.

### Step 1: change directories and run a "simple" web server:

If your machine has `Python 2`:

```sh
$ cd path/to/project/folder
$ python -m SimpleHTTPServer
```

**or**, if you are running `Python 3`:

```sh
$ cd path/to/project/folder
$ python3 -m http.server 8000
```

### Step 2: see your files

* Test your site by navigating to: [http://localhost:8000](http://localhost:8000)

By default, any `index.html` file will be rendered in the browser. If you were to name your HTML file something like `about.html`, that page would be rendered at: `http://localhost:8000/about.html`

***
***
***

## Option 2: Node.js -- http-server module

If you're set up with node.js, personally I find it easier to use the [Node.js http-server module](https://www.npmjs.com/package/http-server) to do exactly the same thing as the python web server above. 

### Step 1: install the `http-server` module

The `http-server` module is a simple module for serving up your static files.

```sh
$ npm install http-server -g
```
the `-g` flag indicates to npm to install globally on your machine.

### Step 2: change directories and run a "http-server"

If you want to use the default port at `8080`:
```sh
$ cd path/to/project/folder
$ http-server
```

you'll see the following output:

```sh
Starting up http-server, serving ./
Available on:
  http://127.0.0.1:8080
  http://192.168.1.169:8080

Hit CTRL-C to stop the server
```

If you want to specify a port, you can do:

```sh
$ cd path/to/project/folder
$ http-server -p 3000
```

And you'll see:

```sh
Starting up http-server, serving ./
Available on:
  http://127.0.0.1:3000
  http://192.168.1.169:3000
Hit CTRL-C to stop the server
```

***
***
***

## Option 3: Node.js -- live-server package

The `live-server module` does the same things as the following 2 options however, it will watch for changes in your project directory and reload your page. This can be really helpful for front-end development so you don't have to reload your page manually every time you change something. 

### Step 1: install the "live-server" module

```sh
$ npm install live-server -g
```
the `-g` flag indicates to npm to install globally on your machine.

### Step 2: change directories and run a "live-server"

If you want to use the default port at `8080`:
```sh
$ cd path/to/project/folder
$ http-server
```

you'll see the following output:

```sh
Serving "/path/to/folder" at http://127.0.0.1:8080
```

If you want to specify a port, you can do:

```sh
$ cd path/to/project/folder
$ http-server --port=3000
```

And you'll see:

```sh
Serving "/path/to/folder" at http://127.0.0.1:3000
```
