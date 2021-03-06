# npmdoc-gulp-awspublish

#### basic api documentation for  [gulp-awspublish (v3.3.0)](https://github.com/pgherveou/gulp-awspublish)  [![npm package](https://img.shields.io/npm/v/npmdoc-gulp-awspublish.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-gulp-awspublish) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-gulp-awspublish.svg)](https://travis-ci.org/npmdoc/node-npmdoc-gulp-awspublish)

#### gulp plugin to publish files to amazon s3

[![NPM](https://nodei.co/npm/gulp-awspublish.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/gulp-awspublish)

- [https://npmdoc.github.io/node-npmdoc-gulp-awspublish/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-gulp-awspublish/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-gulp-awspublish/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-gulp-awspublish/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-gulp-awspublish/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-gulp-awspublish/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "PG Herveou",
        "url": "https://github.com/pgherveou"
    },
    "bugs": {
        "url": "https://github.com/pgherveou/gulp-awspublish/issues"
    },
    "dependencies": {
        "aws-sdk": "^2.1.16",
        "clone": "^1.0.2",
        "gulp-util": "^3.0.7",
        "mime": "^1.3.4",
        "pad-component": "^0.0.1",
        "pascal-case": "^2.0.0",
        "pumpify": "^1.3.5",
        "through2": "^2.0.1",
        "vinyl": "^1.1.1",
        "xml-nodes": "^0.1.5",
        "xml-objects": "^1.0.1"
    },
    "description": "gulp plugin to publish files to amazon s3",
    "devDependencies": {
        "chai": "*",
        "concurrent-transform": "^1.0.0",
        "coveralls": "*",
        "event-stream": "^3.2.1",
        "gulp": "^3.9.0",
        "gulp-rename": "*",
        "istanbul": "*",
        "mocha": "*",
        "mocha-lcov-reporter": "*"
    },
    "directories": {},
    "dist": {
        "shasum": "29935d2915db859450c0c6c80f9c6fb6d0e6d0db",
        "tarball": "https://registry.npmjs.org/gulp-awspublish/-/gulp-awspublish-3.3.0.tgz"
    },
    "engines": {
        "node": ">=0.12.0",
        "npm": ">=1.2.10"
    },
    "gitHead": "97deeebaa91515e7a43395daad13295a76090a68",
    "homepage": "https://github.com/pgherveou/gulp-awspublish",
    "keywords": [
        "gulpplugin",
        "aws",
        "s3",
        "publish"
    ],
    "licenses": [
        {
            "type": "MIT"
        }
    ],
    "main": "./lib/index.js",
    "maintainers": [
        {
            "name": "alexgorbatchev"
        },
        {
            "name": "pgherveou"
        },
        {
            "name": "richardotvos"
        }
    ],
    "name": "gulp-awspublish",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git://github.com/pgherveou/gulp-awspublish.git"
    },
    "scripts": {
        "coveralls": "istanbul cover ./node_modules/mocha/bin/_mocha --report lcovonly -- -R spec && cat ./coverage/lcov.info | ./node_modules/coveralls/bin/coveralls.js && rm -rf ./coverage",
        "test": "istanbul test _mocha --report html -- test/*.js --reporter spec"
    },
    "version": "3.3.0",
    "bin": {}
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
