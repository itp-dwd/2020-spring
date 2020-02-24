# Guide to debugging using the Node Inspector

Adapted from [Debugging Node.js with Chrome Dev Tools](https://medium.com/@paul_irish/debugging-node-js-nightlies-with-chrome-devtools-7c4a1b95ae27).

When you're using Node, you can debug using `console.log`, but you can't add breakpoints/use `debugger` statements unless you use the Node inspector. 

## Steps

1. Determine the file that you want to inspect.
2. run `node --inspect-brk file_name.js`
3. Open a new Chrome window and type `chrome://inspect`
4. You now have access to all of the [Dev Tools](./dev-tools.md) features, within the context of `file_name.js`!
5. 