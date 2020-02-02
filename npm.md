- [Creating a scoped public npm package](https://docs.npmjs.com/creating-and-publishing-scoped-public-packages)
   - npm init
   - npm login  //input username passward
   - npm publish --access public


- [How to fork & patch npm modules](http://debuggable.com/posts/how-to-fork-patch-npm-modules:4e2eb9f3-e584-44be-b1a9-3db7cbdd56cb)
   - Fork the project on GitHub
   - Clone the fork to your machine
   - Fix the bug or add the feature you want
   - Push your commits up to your fork on GitHub
   - Open your fork on GitHub, and click on the latest commit you made
   - On the page of that commit, click on the "Downloads" button
   - Right click on the "Download .tar.gz" button inside the popup, and copy the link ("Copy Link Address" in Chrome)
   - Open up your package.json file, and replace the version number of the module with the url you just copied
   - Send a pull request upstream (Optional, but this way you will avoid having to maintain that patch of yours against newer versions of the module you forked)
   ``` 
   Example: My new airbrake module uses a forked version of xmlbuilder. I submited my fix as a pull request, but it has not been merged yet. In order to pull in my changes via npm anyway, I simply pointed my package.json to the download url of my fork on GitHub like so:
   ``` 
   ``` 
   "dependencies": {
    "request": "1.9.8",
    "xmlbuilder": "https://github.com/felixge/xmlbuilder-js/tarball/4303eb2650a4b819a980b1dc9d2965862a1e9faf",
    "stack-trace": "0.0.5",
    "traverse": "0.4.4",
    "hashish": "0.0.4"
  },
   ``` 
- [Fork and patch npm moduels hosted on GitHub](https://coderwall.com/p/q_gh-w/fork-and-patch-npm-moduels-hosted-on-github) 
- [how-to-use-fork-version-of-npm-package-in-a-project](https://stackoverflow.com/questions/47122349/how-to-use-fork-version-of-npm-package-in-a-project) 

