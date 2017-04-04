# api documentation for  [gulp-awspublish (v3.3.0)](https://github.com/pgherveou/gulp-awspublish)  [![npm package](https://img.shields.io/npm/v/npmdoc-gulp-awspublish.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-gulp-awspublish) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-gulp-awspublish.svg)](https://travis-ci.org/npmdoc/node-npmdoc-gulp-awspublish)
#### gulp plugin to publish files to amazon s3

[![NPM](https://nodei.co/npm/gulp-awspublish.png?downloads=true)](https://www.npmjs.com/package/gulp-awspublish)

[![apidoc](https://npmdoc.github.io/node-npmdoc-gulp-awspublish/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-gulp-awspublish_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-gulp-awspublish/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-gulp-awspublish/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-gulp-awspublish/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "PG Herveou",
        "email": "pg@jogabo.com",
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
            "name": "alexgorbatchev",
            "email": "alex.gorbatchev@gmail.com"
        },
        {
            "name": "pgherveou",
            "email": "pgherveou@gmail.com"
        },
        {
            "name": "richardotvos",
            "email": "otvos.richard@gmail.com"
        }
    ],
    "name": "gulp-awspublish",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/pgherveou/gulp-awspublish.git"
    },
    "scripts": {
        "coveralls": "istanbul cover ./node_modules/mocha/bin/_mocha --report lcovonly -- -R spec && cat ./coverage/lcov.info | ./node_modules/coveralls/bin/coveralls.js && rm -rf ./coverage",
        "test": "istanbul test _mocha --report html -- test/*.js --reporter spec"
    },
    "version": "3.3.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module gulp-awspublish](#apidoc.module.gulp-awspublish)
1.  [function <span class="apidocSignatureSpan">gulp-awspublish.</span>_buildDeleteMultiple (keys)](#apidoc.element.gulp-awspublish._buildDeleteMultiple)
1.  [function <span class="apidocSignatureSpan">gulp-awspublish.</span>_toAwsParams (file)](#apidoc.element.gulp-awspublish._toAwsParams)
1.  [function <span class="apidocSignatureSpan">gulp-awspublish.</span>create (AWSConfig, cacheOptions)](#apidoc.element.gulp-awspublish.create)
1.  [function <span class="apidocSignatureSpan">gulp-awspublish.</span>gzip (options)](#apidoc.element.gulp-awspublish.gzip)
1.  [function <span class="apidocSignatureSpan">gulp-awspublish.</span>reporter (param)](#apidoc.element.gulp-awspublish.reporter)



# <a name="apidoc.module.gulp-awspublish"></a>[module gulp-awspublish](#apidoc.module.gulp-awspublish)

#### <a name="apidoc.element.gulp-awspublish._buildDeleteMultiple"></a>[function <span class="apidocSignatureSpan">gulp-awspublish.</span>_buildDeleteMultiple (keys)](#apidoc.element.gulp-awspublish._buildDeleteMultiple)
- description and source-code
```javascript
function buildDeleteMultiple(keys) {
  if (!keys || !keys.length) return;

  var deleteObjects = keys.map(function (k) { return { Key: k }; });

  return {
    Delete: {
      Objects: deleteObjects
    }
  };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gulp-awspublish._toAwsParams"></a>[function <span class="apidocSignatureSpan">gulp-awspublish.</span>_toAwsParams (file)](#apidoc.element.gulp-awspublish._toAwsParams)
- description and source-code
```javascript
function toAwsParams(file) {
  var params = {};

  var headers = file.s3.headers || {};

  for (var header in headers) {
    if (header === 'x-amz-acl') {

      params.ACL = headers[header];
    } else if(header ==='Content-MD5') {

       params['ContentMD5'] = headers[header];
    } else {

      params[pascalCase(header)] = headers[header];
    }
  }

  params.Key = file.s3.path;
  params.Body = file.contents;

  return params;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gulp-awspublish.create"></a>[function <span class="apidocSignatureSpan">gulp-awspublish.</span>create (AWSConfig, cacheOptions)](#apidoc.element.gulp-awspublish.create)
- description and source-code
```javascript
create = function (AWSConfig, cacheOptions){
  return new Publisher(AWSConfig, cacheOptions);
}
```
- example usage
```shell
...
'''javascript
var awspublish = require('gulp-awspublish');

gulp.task('publish', function() {

// create a new publisher using S3 options
// http://docs.aws.amazon.com/AWSJavaScriptSDK/latest/AWS/S3.html#constructor-property
var publisher = awspublish.create({
  region: 'your-region-id',
  params: {
    Bucket: '...'
  }
}, {
  cacheFileName: 'your-cache-location'
});
...
```

#### <a name="apidoc.element.gulp-awspublish.gzip"></a>[function <span class="apidocSignatureSpan">gulp-awspublish.</span>gzip (options)](#apidoc.element.gulp-awspublish.gzip)
- description and source-code
```javascript
gzip = function (options) {

  if (!options) options = {};
  if (!options.ext) options.ext = '';

  return through.obj(function (file, enc, cb) {

    // Do nothing if no contents
    if (file.isNull()) return cb();

    // streams not supported
    if (file.isStream()) {
      this.emit('error',
        new gutil.PluginError(PLUGIN_NAME, 'Stream content is not supported'));
      return cb();
    }

    // check if file.contents is a 'Buffer'
    if (file.isBuffer()) {

      initFile(file);

      // add content-encoding header
      file.s3.headers['Content-Encoding'] = 'gzip';

      // zip file
      zlib.gzip(file.contents, options, function(err, buf) {
        if (err) return cb(err);
        file.unzipPath = file.path;
        file.path += options.ext;
        file.s3.path += options.ext;
        file.contents = buf;
        cb(err, file);
      });
    }
  });
}
```
- example usage
```shell
...
  var headers = {
'Cache-Control': 'max-age=315360000, no-transform, public'
// ...
  };

  return gulp.src('./public/*.js')
 // gzip, Set Content-Encoding headers and add .gz extension
.pipe(awspublish.gzip({ ext: '.gz' }))

// publisher will add Content-Length, Content-Type and headers specified above
// If not specified it will set x-amz-acl to public-read by default
.pipe(publisher.publish(headers))

// create a cache file to speed up consecutive uploads
.pipe(publisher.cache())
...
```

#### <a name="apidoc.element.gulp-awspublish.reporter"></a>[function <span class="apidocSignatureSpan">gulp-awspublish.</span>reporter (param)](#apidoc.element.gulp-awspublish.reporter)
- description and source-code
```javascript
reporter = function (param) {
  return require('./log-reporter')(param);
}
```
- example usage
```shell
...
    // If not specified it will set x-amz-acl to public-read by default
    .pipe(publisher.publish(headers))

    // create a cache file to speed up consecutive uploads
    .pipe(publisher.cache())

     // print upload updates to console
    .pipe(awspublish.reporter());
});

// output
// [gulp] [create] file1.js.gz
// [gulp] [create] file2.js.gz
// [gulp] [update] file3.js.gz
// [gulp] [cache]  file3.js.gz
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
