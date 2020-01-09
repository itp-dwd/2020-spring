# Installing and Using Node.js with NVM

nvm, or Node Version Manager, is a tool for installing different versions of Node.js. Node.js updates happen quite frequently, and often times working on different Node projects requires using different versions of Node. You can instal Node using the [official installer](https://nodejs.org/en/download/) but it is recommended you use nvm. 

## Installing Node.js with NVM

### Mac or Linux
Simply copy and paste the following line into your terminal application and hit enter:
```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.2/install.sh | bash
```
and that's it!

### Windows
It is recommended that you use Windows Subsystem for Linux 2, therefore your installation steps should be the same.

## Using Node.js with NVM

To install the recommended LTS (long-term support) version of node, which is more stable than the latest version, run
```sh
nvm install --lts
```

You can also install a specific version like
```sh
nvm install 12.14.1
```

To then set the node version to the LTS version, you can run
```sh
nvm use lts/*
```

You can also set a specific version like
```sh
nvm use 12.14.1
```

Then, you'll be able to get to the Node REPL (Read-eval-print loop) by running
```sh
node
```
This is the same as the JavaScript console you'll encounter in any browser, with a different context. 

If you create a JS file, say `script.js`, that looks something like this
```js
let radius = 5;
console.log('The radius of the circle is ' + radius);
```
You can run it with the following command (assuming you're located in the same directory as `script.js`)
```sh
node script.js
```

Note that `nvm use <version>` does not set the **default** node version, which is loaded every time you open a new terminal session. It's important that you set a default node version! When you open a new terminal window, you create a new terminal session. If you had two terminal windows open, and in one, you ran `nvm use 12.14.1` and in the other you ran `nvm use 13.6.0`, different versions of node will be run in the different terminal windows when you run `node`. 

To set the default to LTS, run
```sh
nvm alias default lts/*
```

Or to set the default to a specific version, run
```sh
nvm alias default 12.14.1
```