# Developer Setup Guide

## ABOUT

This setup guide includes resources to get you up and started with all the tools and things you need to be the best developer you can be. 



## QUICKSTART

Get up and running with the some essential development tools to make start taking your web development skills from zero to amazing.

Along with having your **laptop** AND **charger**...

| Pre-installed | Item | Tool | Description | Image |
| :--- | --- | --- |   ---   | --- |
|☑️| Text Editor | [VS Code - Visual Studio Code](https://code.visualstudio.com/) | Supercharged text editor for making your coding dreams come true | ![VS Code Screenshot](https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fcode.visualstudio.com%2Fopengraphimg%2Fopengraph-home.png&f=1&nofb=1) |
|☑️| Web Browser | [Chrome Download](https://www.google.com/chrome/) | **Web browser** (chrome or firefox preferred, but safari is ok): as a developer, you should be testing with multiple browsers! Please make sure to have both Chrome and Firefox at least. | ![Google Chrome Browser](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fs4827.pcdn.co%2Fwp-content%2Fuploads%2F2019%2F12%2FChrome_BlogHeader_PasswordManager-800x457.jpg&f=1&nofb=1) 
|☑️| Web Browser | [Firefox Download](https://www.mozilla.org/en-US/firefox/new/) | **Web browser** (chrome or firefox preferred, but safari is ok): as a developer, you should be testing with multiple browsers! Please make sure to have both Chrome and Firefox at least. | ![Firefox Browser](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fi.ytimg.com%2Fvi%2FsHxsVx1RVDY%2Fmaxresdefault.jpg&f=1&nofb=1)
|✅| Command line OR Terminal | Command Line or Terminal | Text based interface to your machine's inner workings | ![Commandline](https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fgetintopc.com%2Fwp-content%2Fuploads%2F2016%2F02%2FWindows-10-Redstone-1-14257-ISO-x86-x64-AIO-30in1-Direct-Link-Download.png&f=1&nofb=1) OR  ![Mac Terminal](/assets/commandline-01.png) 
|✅| Git | [Git homepage](https://git-scm.com/) | Git is a version control system - this should be natively installed on your computers by default | ![git logo](https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fsiliconangle.com%2Ffiles%2F2013%2F05%2Fgit-logo.jpg&f=1&nofb=1)  |
|☑️| Github | [Sign up with Github.com](https://github.com/) | Collaborative software development platform | ![Github Logo](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwww.tecmint.com%2Fwp-content%2Fuploads%2F2013%2F10%2FInstall-GitHub.jpeg&f=1&nofb=1) |
|☑️| Student Developer Pack | [[Student Developer Pack](https://education.github.com/pack) | Lots of free offerings for students for software development - take advatnage of these benefits while you can! | ![Github student developer pack](https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fpcguide.wpengine.com%2Fwp-content%2Fuploads%2Fgithub-student-developer-pack.png&f=1&nofb=1)  |
|☑️| Platform as a Service | [Sign up with Glitch.com](https://glitch.com/) | When building web applications you'll need a web hosting service that can provide a platform to host your server side code. | ![Glitch App](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftheegent.com%2Fwp-content%2Fuploads%2F2019%2F07%2Fcoding-remix-site-glitch-hits-2-5-million-apps.jpg&f=1&nofb=1)  |
|✅ | Simple Web Server | [See Simple Web Server Guide](/guides/quick-web-servers.md) |   A simple web server allows you to serve up your local HTML/CSS/JavaScript for development and testing  | --- |





## Beyond the Quickstart

In addition to the materials in the [Quickstart](#quickstart), these materials are necessary for developing your fullstack web applications:

| Pre-installed | Item | Tool | Description | Image |
| :--- | --- | --- |   ---   | --- |
|☑️| Node.js | [Node.js installed with NVM](installing-nodejs.md) | Server side JavaScript | | 
|☑️| XCode | Mac only - XCode | Mac only - Mac Developer Toolkit - a Dependency for Homebrew (below) | | 
|☑️| Homebrew | Mac only - Software Package Manager | Mac only - Software Package Manager | | 
|☑️| NoSQL Database | [Download MongDB](https://www.mongodb.com/download-center/community) or [Install MongoDB via Homebrew](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/) | MongoDB is a database | | 
|☑️| Database as a service | [MongoDB Atlas](https://docs.atlas.mongodb.com/tutorial/create-atlas-account/) | MongoDB Atlas provides an easy way to host and manage your data in the cloud.  | ![Mongodb Atlas](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fimage.codeforgeek.com%2Fwp-content%2Fuploads%2F2018%2F03%2FMongoDB-Atlas.png&f=1&nofb=1) |


<!-- 
* Laptop & Power charger
* **Text Editor** (VS Code):
  * [VS Code - Visual Studio Code](https://code.visualstudio.com/)
  * ![VS Code Screenshot](https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fcode.visualstudio.com%2Fopengraphimg%2Fopengraph-home.png&f=1&nofb=1)
* **Web browser** (chrome or firefox preferred, but safari is ok): as a developer, you should be testing with multiple browsers! Please make sure to have both Chrome and Firefox at least.
  * [Chrome Download](https://www.google.com/chrome/)
    * ![Google Chrome Browser](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fs4827.pcdn.co%2Fwp-content%2Fuploads%2F2019%2F12%2FChrome_BlogHeader_PasswordManager-800x457.jpg&f=1&nofb=1)
  * [Firefox Download](https://www.mozilla.org/en-US/firefox/new/)
    * ![Firefox Browser](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fi.ytimg.com%2Fvi%2FsHxsVx1RVDY%2Fmaxresdefault.jpg&f=1&nofb=1)
* **Command Line Interface**
  * On Mac, this is your "Terminal" application.
    * ![Mac Terminal](/assets/commandline-01.png)
  * On Windows, you must set up [Windows Subsystem for Linux 2](https://docs.microsoft.com/en-us/windows/nodejs/setup-on-wsl2)
    * ![Commandline](https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fgetintopc.com%2Fwp-content%2Fuploads%2F2016%2F02%2FWindows-10-Redstone-1-14257-ISO-x86-x64-AIO-30in1-Direct-Link-Download.png&f=1&nofb=1)
* **GitHub Account**:
  * [Sign up with Github.com](https://github.com/)
  * [Student Developer Pack](https://education.github.com/pack)

* **Github Desktop Tool**:
  * [Download Github Desktop](https://desktop.github.com/)
* **Glitch Account**:
  * [Sign up with Glitch.com](https://glitch.com/) -->


## ✏️ Web Design Tools

| Purpose | Tool | Description | Key Features | Image |
| :--- | --- | --- | --- | --- |
| Design & Prototype | [Figma](https://www.figma.com/) | Design and prototype in tandem. Bring your ideas to life faster in animated prototypes that feel like the real thing. Get insights from users and test concepts earlier and more often. | --- |![Figma Interface Screenshot](https://i.vimeocdn.com/video/822590268.jpg?mw=1200&mh=686) |
Design & Prototype | [Sketch App](https://www.sketch.com/) |  Sketch is built for designers like you. From essential tools that help you work faster, to game-changing features that empower teams around the world, we've built the definitive platform for digital design. | --- | ![Sketch Interface Screenshot](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fnewbirddesign.com%2Fapp%2Fuploads%2F2017%2F01%2FSketch-Pages.jpeg&f=1&nofb=1)
| Prototyping & Screen Flow | [Invision](https://www.invisionapp.com/) | Create rich interactive prototypes from sketch files | --- | ![Invision Interface Screenshot](https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fwww.onextrapixel.com%2Fwp-content%2Fuploads%2F2015%2F10%2FInvisionapp-2.jpg&f=1&nofb=1) |
| Prototyping | [Framer](https://www.framer.com/) | Bring your creative ideas to life with Framer X, the best tool for interactive design. Create responsive layouts, design realistic prototypes, and bring everything closer to production—all in one place | --- | ![Framer Interface Screenshot](https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fframer.com%2Fassets%2Fstatic%2Fimages%2Fsocial%2Fframer.png&f=1&nofb=1) |
| Design & CMS | [Webflow](https://webflow.com/) & [Webflow Designer](https://webflow.com/designer)| Take control of HTML5, CSS3, and JavaScript in a completely visual canvas — and let Webflow translate your design into clean, semantic code that’s ready to publish to the web, or hand off to developers. | --- | --- |


<!-- * [Figma](https://www.figma.com/)
  * Design and prototype in tandem. Bring your ideas to life faster in animated prototypes that feel like the real thing. Get insights from users and test concepts earlier and more often.
  * ![Figma Interface Screenshot](https://i.vimeocdn.com/video/822590268.jpg?mw=1200&mh=686)
* [Sketch App](https://www.sketch.com/)
  * Sketch is built for designers like you. From essential tools that help you work faster, to game-changing features that empower teams around the world, we've built the definitive platform for digital design.
  * ![Sketch Interface Screenshot](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fnewbirddesign.com%2Fapp%2Fuploads%2F2017%2F01%2FSketch-Pages.jpeg&f=1&nofb=1)
* [Invision](https://www.invisionapp.com/)
  * Create rich interactive prototypes from sketch files
  * ![Invision Interface Screenshot](https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fwww.onextrapixel.com%2Fwp-content%2Fuploads%2F2015%2F10%2FInvisionapp-2.jpg&f=1&nofb=1)
* [Framer](https://www.framer.com/)
  * Bring your creative ideas to life with Framer X, the best tool for interactive design. Create responsive layouts, design realistic prototypes, and bring everything closer to production—all in one place
  * ![Framer Interface Screenshot](https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fframer.com%2Fassets%2Fstatic%2Fimages%2Fsocial%2Fframer.png&f=1&nofb=1)
 -->



## 🛠 Development Tools 

* RunJS: 
  * A tool for running javascript in an interactive environment on your machine. Very cool for testing code
  * https://runjs.dev/
* JSON Placeholder API:
  * https://jsonplaceholder.typicode.com/
  * /users: https://jsonplaceholder.typicode.com/users
  

## 📷 Documentation Tools

* Screenshots: OS based Screenshots
  * On MacOS:
    * to capture the entire screen: `shift` + `command` + `3`
    * to interactive capture using your mouse: `shift` + `command` + `4`
    * to capture a selected window: `shift` + `command` + `4` + `spacebar` > click on the window you want to capture
  * On Windows:
    * See [Microsoft Screenshot](https://www.microsoft.com/en-us/p/screenshot/9wzdncrdqjfq?activetab=pivot:overviewtab#)
* [Giphy Capture](https://giphy.com/apps/giphycapture)
  * Gifs are a great way to document dynamic web pages and interaction. We can recommend using [Giphy Capture](https://giphy.com/apps/giphycapture) to create gifs documentation for your websites and web apps as well as for any process based documentation you're creating for your READMEs. See: [Giphy Capture](https://giphy.com/apps/giphycapture).
* [Open Broadcast Studio - OBS](https://obsproject.com/)
  * [Open Broadcast Studio - OBS](https://obsproject.com/) is a free software for doing screen recordings. Highly recommended for doing screen recordings and if you want to make multiple views (e.g. screen capture while recording your face using the web cam). See [OBS](https://obsproject.com/).
