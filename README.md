# api documentation for  [chai-http (v3.0.0)](https://github.com/chaijs/chai-http#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-chai-http.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-chai-http) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-chai-http.svg)](https://travis-ci.org/npmdoc/node-npmdoc-chai-http)
#### Extend Chai Assertion library with tests for http apis

[![NPM](https://nodei.co/npm/chai-http.png?downloads=true)](https://www.npmjs.com/package/chai-http)

[![apidoc](https://npmdoc.github.io/node-npmdoc-chai-http/build/screenCapture.buildNpmdoc.browser.%2Fhome%2Ftravis%2Fbuild%2Fnpmdoc%2Fnode-npmdoc-chai-http%2Ftmp%2Fbuild%2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-chai-http/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-chai-http/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-chai-http/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Jake Luer",
        "email": "jake@alogicalparadox.com"
    },
    "browser": {
        "http": false,
        "https": false,
        "net": "./lib/net.js",
        "querystring": "qs"
    },
    "bugs": {
        "url": "https://github.com/chaijs/chai-http/issues"
    },
    "contributors": [
        {
            "name": "Jake Luer",
            "email": "jake@alogicalparadox.com"
        },
        {
            "name": "Veselin Todorov",
            "email": "hi@vesln.com"
        },
        {
            "name": "Keith Cirkel",
            "email": "oss@keithcirkel.co.uk",
            "url": "http://keithcirkel.co.uk"
        }
    ],
    "dependencies": {
        "cookiejar": "2.0.x",
        "is-ip": "1.0.0",
        "methods": "^1.1.2",
        "qs": "^6.2.0",
        "superagent": "^2.0.0"
    },
    "description": "Extend Chai Assertion library with tests for http apis",
    "devDependencies": {
        "chai": "*",
        "coveralls": "^2.11.9",
        "dox": "^0.8.1",
        "es6-shim": "^0.35.1",
        "http-server": "^0.9.0",
        "istanbul": "^0.4.3",
        "mocha": "^2.5.3",
        "npm-run-all": "^2.1.1",
        "simplifyify": "^2.0.1"
    },
    "directories": {},
    "dist": {
        "shasum": "5460d8036e1f1a12b0b5b5cbd529e6dc1d31eb4b",
        "tarball": "https://registry.npmjs.org/chai-http/-/chai-http-3.0.0.tgz"
    },
    "engines": {
        "node": ">= 0.6.0"
    },
    "files": [
        "dist/chai-http.js",
        "lib/*.js",
        "index.js"
    ],
    "gitHead": "1345021daad2c7b0fbac9fe5c541f55802795f33",
    "homepage": "https://github.com/chaijs/chai-http#readme",
    "keywords": [
        "chai",
        "chai-plugin",
        "browser",
        "http",
        "request",
        "vendor",
        "supertest",
        "superagent"
    ],
    "main": "./index",
    "maintainers": [
        {
            "name": "chaijs",
            "email": "chaijs@keithcirkel.co.uk"
        }
    ],
    "name": "chai-http",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+ssh://git@github.com/chaijs/chai-http.git"
    },
    "scripts": {
        "build": "npm run build:readme && npm run build:js",
        "build:js": "simplifyify lib/http.js --outfile dist/chai-http.js --bundle --minify --debug --standalone chaiHttp",
        "build:readme": "rm -rf README.md && node ./support/readme",
        "posttest": "if [ -z \"$COVERALLS_REPO_TOKEN\" ]; then cat coverage/lcov.info | coveralls; fi",
        "prebuild:js": "rm -rf dist",
        "server": "http-server -o -c-1",
        "start": "npm-run-all --parallel watch server",
        "test": "istanbul cover --report lcovonly _mocha",
        "watch": "npm run build:js -- --watch"
    },
    "version": "3.0.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module chai-http](#apidoc.module.chai-http)
1.  [function <span class="apidocSignatureSpan">chai-http.</span>request (app)](#apidoc.element.chai-http.request)
1.  object <span class="apidocSignatureSpan">chai-http.</span>net

#### [module chai-http.net](#apidoc.module.chai-http.net)
1.  [function <span class="apidocSignatureSpan">chai-http.net.</span>isIP (str)](#apidoc.element.chai-http.net.isIP)
1.  [function <span class="apidocSignatureSpan">chai-http.net.</span>isIPv4 (str)](#apidoc.element.chai-http.net.isIPv4)
1.  [function <span class="apidocSignatureSpan">chai-http.net.</span>isIPv6 (str)](#apidoc.element.chai-http.net.isIPv6)

#### [module chai-http.request](#apidoc.module.chai-http.request)
1.  [function <span class="apidocSignatureSpan">chai-http.</span>request (app)](#apidoc.element.chai-http.request.request)
1.  [function <span class="apidocSignatureSpan">chai-http.request.</span>Request (app, method, path)](#apidoc.element.chai-http.request.Request)
1.  [function <span class="apidocSignatureSpan">chai-http.request.</span>Test (app, method, path)](#apidoc.element.chai-http.request.Test)
1.  [function <span class="apidocSignatureSpan">chai-http.request.</span>agent (app)](#apidoc.element.chai-http.request.agent)



# <a name="apidoc.module.chai-http"></a>[module chai-http](#apidoc.module.chai-http)

#### <a name="apidoc.element.chai-http.request"></a>[function <span class="apidocSignatureSpan">chai-http.</span>request (app)](#apidoc.element.chai-http.request)
- description and source-code
```javascript
request = function (app) {

<span class="apidocCodeCommentSpan">  /*!
   * @param {Mixed} function or server
   * @returns {Object} API
   */
</span>
  var server = ('function' === typeof app)
      ? http.createServer(app)
      : app
    , obj = {};

  methods.forEach(function (method) {
    obj[method] = function (path) {
      return new Test(server, method, path);
    };
  });
  obj.del = obj.delete;

  return obj;
}
```
- example usage
```shell
...
* or a node.js http(s) server as the foundation for your request.
* If the server is not running, chai-http will find a suitable
* port to listen on for a given test.
*
* __Note:__ This feature is only supported on Node.js, not in web browsers.
*
* '''js
* chai.request(app)
*   .get('/')
* '''
*
* #### URL
*
* You may also use a base url as the foundation of your request.
*
...
```



# <a name="apidoc.module.chai-http.net"></a>[module chai-http.net](#apidoc.module.chai-http.net)

#### <a name="apidoc.element.chai-http.net.isIP"></a>[function <span class="apidocSignatureSpan">chai-http.net.</span>isIP (str)](#apidoc.element.chai-http.net.isIP)
- description and source-code
```javascript
isIP = function (str) {
	return ipRegex({exact: true}).test(str);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.chai-http.net.isIPv4"></a>[function <span class="apidocSignatureSpan">chai-http.net.</span>isIPv4 (str)](#apidoc.element.chai-http.net.isIPv4)
- description and source-code
```javascript
isIPv4 = function (str) {
	return ipRegex.v4({exact: true}).test(str);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.chai-http.net.isIPv6"></a>[function <span class="apidocSignatureSpan">chai-http.net.</span>isIPv6 (str)](#apidoc.element.chai-http.net.isIPv6)
- description and source-code
```javascript
isIPv6 = function (str) {
	return ipRegex.v6({exact: true}).test(str);
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.chai-http.request"></a>[module chai-http.request](#apidoc.module.chai-http.request)

#### <a name="apidoc.element.chai-http.request.request"></a>[function <span class="apidocSignatureSpan">chai-http.</span>request (app)](#apidoc.element.chai-http.request.request)
- description and source-code
```javascript
request = function (app) {

<span class="apidocCodeCommentSpan">  /*!
   * @param {Mixed} function or server
   * @returns {Object} API
   */
</span>
  var server = ('function' === typeof app)
      ? http.createServer(app)
      : app
    , obj = {};

  methods.forEach(function (method) {
    obj[method] = function (path) {
      return new Test(server, method, path);
    };
  });
  obj.del = obj.delete;

  return obj;
}
```
- example usage
```shell
...
* or a node.js http(s) server as the foundation for your request.
* If the server is not running, chai-http will find a suitable
* port to listen on for a given test.
*
* __Note:__ This feature is only supported on Node.js, not in web browsers.
*
* '''js
* chai.request(app)
*   .get('/')
* '''
*
* #### URL
*
* You may also use a base url as the foundation of your request.
*
...
```

#### <a name="apidoc.element.chai-http.request.Request"></a>[function <span class="apidocSignatureSpan">chai-http.request.</span>Request (app, method, path)](#apidoc.element.chai-http.request.Request)
- description and source-code
```javascript
function Test(app, method, path) {
  Request.call(this, method, path);
  this.app = app;
  this.url = typeof app === 'string' ? app + path : serverAddress(app, path);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.chai-http.request.Test"></a>[function <span class="apidocSignatureSpan">chai-http.request.</span>Test (app, method, path)](#apidoc.element.chai-http.request.Test)
- description and source-code
```javascript
function Test(app, method, path) {
  Request.call(this, method, path);
  this.app = app;
  this.url = typeof app === 'string' ? app + path : serverAddress(app, path);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.chai-http.request.agent"></a>[function <span class="apidocSignatureSpan">chai-http.request.</span>agent (app)](#apidoc.element.chai-http.request.agent)
- description and source-code
```javascript
function TestAgent(app) {
  if (!(this instanceof TestAgent)) return new TestAgent(app);
  if (typeof app === 'function') app = http.createServer(app);
  (Agent || Request).call(this);
  this.app = app;
}
```
- example usage
```shell
...
*   chai.request.addPromises(q.Promise);
* }
* '''
*
* #### Retaining cookies with each request
*
* Sometimes you need to keep cookies from one request, and send them with the
* next. For this, '.request.agent()' is available:
*
* '''js
* // Log in
* var agent = chai.request.agent(app)
* agent
*   .post('/session')
*   .send({ username: 'me', password: '123' })
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
