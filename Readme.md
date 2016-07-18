# [browserfs-module](https://github.com/Narazaka/browserfs-module.js)

[![npm](https://img.shields.io/npm/v/browserfs-module.svg)](https://www.npmjs.com/package/browserfs-module)
[![npm license](https://img.shields.io/npm/l/browserfs-module.svg)](https://www.npmjs.com/package/browserfs-module)
[![npm download total](https://img.shields.io/npm/dt/browserfs-module.svg)](https://www.npmjs.com/package/browserfs-module)
[![npm download by month](https://img.shields.io/npm/dm/browserfs-module.svg)](https://www.npmjs.com/package/browserfs-module)
[![Bower](https://img.shields.io/bower/v/browserfs-module.svg)](https://github.com/Narazaka/browserfs-module.js)
[![Bower](https://img.shields.io/bower/l/browserfs-module.svg)](https://github.com/Narazaka/browserfs-module.js)

[![Dependency Status](https://david-dm.org/Narazaka/browserfs-module.js.svg)](https://david-dm.org/Narazaka/browserfs-module.js)
[![devDependency Status](https://david-dm.org/Narazaka/browserfs-module.js/dev-status.svg)](https://david-dm.org/Narazaka/browserfs-module.js#info=devDependencies)
[![Travis Build Status](https://travis-ci.org/Narazaka/browserfs-module.js.svg)](https://travis-ci.org/Narazaka/browserfs-module.js)
[![AppVeyor Build Status](https://ci.appveyor.com/api/projects/status/github/Narazaka/browserfs-module.js?svg=true)](https://ci.appveyor.com/project/Narazaka/browserfs-module-js)
[![Code Climate](https://codeclimate.com/github/Narazaka/browserfs-module.js/badges/gpa.svg)](https://codeclimate.com/github/Narazaka/browserfs-module.js)

[require()](https://github.com/nodejs/node) with [BrowserFS](https://github.com/jvilk/BrowserFS)

## Install

npm:
```
npm install browserfs-module
```

bower:
```
bower install browserfs-module
```

## Usage

```html
<script src="browserfs.js"></script>
<script src="browserfs-module.js"></script>
<script>
var fsBase = new BrowserFS.FileSystem.InMemory();
BrowserFS.initialize(fsBase);

var fs = BrowserFS.BFSRequire('fs');
fs.writeFileSync('/main.js', 'module.exports = require("sub");');
fs.mkdirSync('/node_modules');
fs.writeFileSync('/node_modules/sub.js' ,'module.exports = "sub required!";');

Module = browserfsModule.Module;
var main = Module._load("/main");
console.log(main); // "sub required!"
</script>
```

## License

This is released under [MIT License](https://narazaka.net/license/MIT?2016).
