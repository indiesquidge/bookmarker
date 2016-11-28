# Bookmarker

A bookmark list application for storing URLs and their respective page titles.

![bookmarker-image](http://i.imgur.com/GWRWWpP.png)

### Run

```
git clone git@github.com:indiesquidge/bookmarker.git
cd bookmarker
npm install
npm start
```

### File Structure

```
.
├── README.md
├── app
│   ├── index.html
│   ├── main.js
│   └── renderer.js
├── assets
│   └── style.css
└── package.json

(difference between `main` and `renderer` described below)
```

### Interesting things learned while building

- Anything you can do in the browser, you can do with Electron. Anything you can do with Node, you can do with Electron. Together, we can build applications that take advantage of both platforms and build applications that wouldn't otherwise be possible on just one.

- Electron allows us to make requests from a third-party server directly from the browser without an intermediary server. Traditional web applications are not permitted to do this.

- Electron is not a framework. This means that it does not provide any scaffolding or have strong opinions about how you structure your application or name your files. Those choice are left up to us, the developers. On the bright side, it also doesn't enforce any conventions either and there is less conceptual boilerplate to discuss before getting our hands dirty.

- The `main` process is responsible for interacting with the operating system, managing state, and coordinating with all of the other processes in our application. It is not in charge of rendering HTML and CSS. This functionality is implemented by `renderer` processes

- Each `BrowserWindow` is a separate and unique `renderer` process that includes a DOM, access to Chromium's Web APIs, and Node's built-in module.

- Our applications will only run inside of the version of Chromium that we ship with the application. We don't have to worry about cross-browser support or legacy compatibility.

- Electron implements module system without any build tools (no webpack, gulp, etc.)

---

This example was built from the tutorial in chapter 2 of Steve Kinney's
_[Electron in Action](https://www.manning.com/books/electron-in-action)_ book.
