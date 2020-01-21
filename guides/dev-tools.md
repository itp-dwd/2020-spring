# Guide to your Browser's Developer Tools

## Table of Contents
- [Guide to your Browser's Developer Tools](#guide-to-your-browsers-developer-tools)
  - [Table of Contents](#table-of-contents)
  - [About](#about)
  - [Getting Started](#getting-started)
  - [Devtools: HTML - The Elements panel](#devtools-html---the-elements-panel)
  - [Devtools: CSS - Styles Panel](#devtools-css---styles-panel)
  - [Devtools: JavaScript Console](#devtools-javascript-console)
  - [Devtools: Everything Else](#devtools-everything-else)
  - [References](#references)

## About

This guide introduces you to your browser's developer tools (a.k.a "devtools") and highlights the key features that will help you develop and debug like a pro.

## Getting Started

To open your browser's devtools, you can open the devtools up by:

* Mozilla Firefox: Open firefox then...
  * type on your keyboard: `option` + `command` + `i`
  * OR navigate there using the menu: `firefox > tools > web developer > toggle tools`
* Google Chrome: Open chrome then...
  * type on your keyboard: `option` + `command` + `i`
  * OR navigate there using the menu: `chrome > settings > more tools > developer tools`
* Safari: Open Safari, go to a webpage of choice, then...
  * type on your keyboard: `option` + `command` + `i`
  * OR navigate there using the menu: `Safari > Preferences, click Advanced, then select “Show Develop menu in menu bar.”`



## Devtools: HTML - The Elements panel

In your devtools you'll be able to examine each and every DOM node. there are different names for the panel to examine your HTML elements (e.g. in Firefox it is called the "inspector" panel whereas in Safari and Chrome it is called the "elements" panel).

![HTML Dev tools screenshot in firefox](/assets/dev-tools__html-01.png)

Here you can add DOM Nodes, edit the text content of DOM Nodes, and inspect which events (if any) have been attached to DOM nodes across your page.

Read more about [Browser dev tools -- HTML Structure and CSS](https://flaviocopes.com/browser-dev-tools/#html-structure-and-css)

## Devtools: CSS - Styles Panel

You can inspect the CSS styles that are applied to DOM nodes on your website in the devtools as well. By clicking on a DOM node in your "elements" or "inspector" panel, you will see a "styles" subpanel showing the relevant CSS styles for that DOM node. You can update those CSS Styles in real-time by adjusting the values of the properties in that panel. This is a handy way of testing variations or additions to CSS styles before adding them in to your code base.

![Dev Tools CSS style update](/assets/dev-tools__css-01.gif)

Read more about [Browser dev tools -- HTML Structure and CSS](https://flaviocopes.com/browser-dev-tools/#the-css-styles-panel)

## Devtools: JavaScript Console

While your devtools will pretty much always be open during frontend web development, the panel you are likely to use the most when developing out your clientside JavaScript is the JavaScript Console panel

The JavaScript Console is the place where any errors in your JavaScript will be flagged, where any of your `console.log()` statements will be logged, where your network requests are going and if they are successful, and where you'll be able to quickly test any JavaScript code you want to write interactively in the console.


**Example of all the network requests logged to the console**:
![Screenshot of dev tools open to Flavio Copes Blog Post](/assets/dev-tools__console-01.png)

**Example of interacting with the DOM using the console**:

![GIF of dev tools - interactive console](/assets/dev-tools__console-02.gif)

Read more about [Browser dev tools -- HTML Structure and CSS](https://flaviocopes.com/browser-dev-tools/#the-console)

## Devtools: Everything Else

Your browser's devtools come with A LOT of other panels that can help you in your development. Other panels and functionality you should look into includes:

* [The Emulator](https://flaviocopes.com/browser-dev-tools/#the-emulator): for testing responsive design for different screen sizes.
* [The Network Panel](https://flaviocopes.com/browser-dev-tools/#the-network-panel): for examining the nature of your network requests - VERY handy for when you're making network requests to APIs etc.
* [JavaScript Debugger](https://flaviocopes.com/browser-dev-tools/#javascript-debugger): If you have an error, you can use the debugger to see where the error is originating in your code
* [Application and Storage](https://flaviocopes.com/browser-dev-tools/#application-and-storage): for info about the data that is stored in your browser depending on which website you're visiting
* [The Security Tab](https://flaviocopes.com/browser-dev-tools/#security-tab): for info about your browser's connection
* [Audits](https://flaviocopes.com/browser-dev-tools/#audits): for auditing your code for accessibiity and performance

## References
* [Overview of the Browser DevTools](https://flaviocopes.com/browser-dev-tools/)
* [What are browser developer tools?](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_are_browser_developer_tools) by Mozilla MDN Docs
* [Chrome developer tools](https://developers.google.com/web/tools/chrome-devtools/) by Google Chrome Developers