# api documentation for  [longjohn (v0.2.12)](https://github.com/mattinsler/longjohn)  [![npm package](https://img.shields.io/npm/v/npmdoc-longjohn.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-longjohn) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-longjohn.svg)](https://travis-ci.org/npmdoc/node-npmdoc-longjohn)
#### Long stack traces for node.js inspired by https://github.com/tlrobinson/long-stack-traces

[![NPM](https://nodei.co/npm/longjohn.png?downloads=true)](https://www.npmjs.com/package/longjohn)

[![apidoc](https://npmdoc.github.io/node-npmdoc-longjohn/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-longjohn_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-longjohn/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-longjohn/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-longjohn/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Matt Insler",
        "email": "matt.insler@gmail.com",
        "url": "http://www.mattinsler.com"
    },
    "bugs": {
        "url": "https://github.com/mattinsler/longjohn/issues"
    },
    "dependencies": {
        "source-map-support": "0.3.2 - 1.0.0"
    },
    "description": "Long stack traces for node.js inspired by https://github.com/tlrobinson/long-stack-traces",
    "devDependencies": {
        "coffee-script": "1.12.2",
        "grunt": "0.4.5",
        "grunt-cli": "1.2.0",
        "grunt-contrib-coffee": "0.7.0",
        "mocha": "3.2.0"
    },
    "directories": {},
    "dist": {
        "shasum": "7ca7446b083655c377e7512213dc754d52a64a7e",
        "tarball": "https://registry.npmjs.org/longjohn/-/longjohn-0.2.12.tgz"
    },
    "engines": {
        "node": ">= 0.9.3"
    },
    "gitHead": "5c7a47963cd042253fff578cbb2d26555870f48c",
    "homepage": "https://github.com/mattinsler/longjohn",
    "keywords": [],
    "license": "MIT",
    "main": "dist/longjohn",
    "maintainers": [
        {
            "name": "mattinsler",
            "email": "matt.insler@gmail.com"
        }
    ],
    "name": "longjohn",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/mattinsler/longjohn.git"
    },
    "scripts": {
        "test": "node_modules/mocha/bin/mocha --compilers coffee:coffee-script/register -R spec"
    },
    "version": "0.2.12"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module longjohn](#apidoc.module.longjohn)
1.  [function <span class="apidocSignatureSpan">longjohn.</span>format_stack (err, frames)](#apidoc.element.longjohn.format_stack)
1.  [function <span class="apidocSignatureSpan">longjohn.</span>format_stack_frame (frame)](#apidoc.element.longjohn.format_stack_frame)
1.  number <span class="apidocSignatureSpan">longjohn.</span>async_trace_limit
1.  string <span class="apidocSignatureSpan">longjohn.</span>empty_frame



# <a name="apidoc.module.longjohn"></a>[module longjohn](#apidoc.module.longjohn)

#### <a name="apidoc.element.longjohn.format_stack"></a>[function <span class="apidocSignatureSpan">longjohn.</span>format_stack (err, frames)](#apidoc.element.longjohn.format_stack)
- description and source-code
```javascript
format_stack = function (err, frames) {
  var e, lines;
  lines = [];
  try {
    lines.push(err.toString());
  } catch (_error) {
    e = _error;
    console.log('Caught error in longjohn. Please report this to matt.insler@gmail.com.');
  }
  lines.push.apply(lines, frames.map(exports.format_stack_frame));
  return lines.join('\n');
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.longjohn.format_stack_frame"></a>[function <span class="apidocSignatureSpan">longjohn.</span>format_stack_frame (frame)](#apidoc.element.longjohn.format_stack_frame)
- description and source-code
```javascript
format_stack_frame = function (frame) {
  if (frame.getFileName() === exports.empty_frame) {
    return exports.empty_frame;
  }
  return '    at ' + source_map.wrapCallSite(frame);
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
