swagger-mongodb
===============
lightweight swagger-ui crud-api backed by mongodb

[![NPM](https://img.shields.io/npm/v/swagger-mongodb.svg?style=flat-square)](https://www.npmjs.org/package/swagger-mongodb)



# live test-server
[![heroku.com test-server](https://kaizhu256.github.io/node-swagger-mongodb/build/screen-capture.testExampleJs.slimerjs..png)](https://hrku01-swagger-mongodb-beta.herokuapp.com)



# build-status [![travis-ci.org build-status](https://api.travis-ci.org/kaizhu256/node-swagger-mongodb.svg)](https://travis-ci.org/kaizhu256/node-swagger-mongodb)

[![build commit status](https://kaizhu256.github.io/node-swagger-mongodb/build/build.badge.svg)](https://travis-ci.org/kaizhu256/node-swagger-mongodb)

| git-branch : | [master](https://github.com/kaizhu256/node-swagger-mongodb/tree/master) | [beta](https://github.com/kaizhu256/node-swagger-mongodb/tree/beta) | [alpha](https://github.com/kaizhu256/node-swagger-mongodb/tree/alpha)|
|--:|:--|:--|:--|
| test-server : | [![heroku.com test-server](https://kaizhu256.github.io/node-swagger-mongodb/heroku-logo.75x25.png)](https://hrku01-swagger-mongodb-master.herokuapp.com) | [![heroku.com test-server](https://kaizhu256.github.io/node-swagger-mongodb/heroku-logo.75x25.png)](https://hrku01-swagger-mongodb-beta.herokuapp.com) | [![heroku.com test-server](https://kaizhu256.github.io/node-swagger-mongodb/heroku-logo.75x25.png)](https://hrku01-swagger-mongodb-alpha.herokuapp.com)|
| test-report : | [![test-report](https://kaizhu256.github.io/node-swagger-mongodb/build..master..travis-ci.org/test-report.badge.svg)](https://kaizhu256.github.io/node-swagger-mongodb/build..master..travis-ci.org/test-report.html) | [![test-report](https://kaizhu256.github.io/node-swagger-mongodb/build..beta..travis-ci.org/test-report.badge.svg)](https://kaizhu256.github.io/node-swagger-mongodb/build..beta..travis-ci.org/test-report.html) | [![test-report](https://kaizhu256.github.io/node-swagger-mongodb/build..alpha..travis-ci.org/test-report.badge.svg)](https://kaizhu256.github.io/node-swagger-mongodb/build..alpha..travis-ci.org/test-report.html)|
| coverage : | [![istanbul-lite coverage](https://kaizhu256.github.io/node-swagger-mongodb/build..master..travis-ci.org/coverage.badge.svg)](https://kaizhu256.github.io/node-swagger-mongodb/build..master..travis-ci.org/coverage.html/index.html) | [![istanbul-lite coverage](https://kaizhu256.github.io/node-swagger-mongodb/build..beta..travis-ci.org/coverage.badge.svg)](https://kaizhu256.github.io/node-swagger-mongodb/build..beta..travis-ci.org/coverage.html/index.html) | [![istanbul-lite coverage](https://kaizhu256.github.io/node-swagger-mongodb/build..alpha..travis-ci.org/coverage.badge.svg)](https://kaizhu256.github.io/node-swagger-mongodb/build..alpha..travis-ci.org/coverage.html/index.html)|
| build-artifacts : | [![build-artifacts](https://kaizhu256.github.io/node-swagger-mongodb/glyphicons_144_folder_open.png)](https://github.com/kaizhu256/node-swagger-mongodb/tree/gh-pages/build..master..travis-ci.org) | [![build-artifacts](https://kaizhu256.github.io/node-swagger-mongodb/glyphicons_144_folder_open.png)](https://github.com/kaizhu256/node-swagger-mongodb/tree/gh-pages/build..beta..travis-ci.org) | [![build-artifacts](https://kaizhu256.github.io/node-swagger-mongodb/glyphicons_144_folder_open.png)](https://github.com/kaizhu256/node-swagger-mongodb/tree/gh-pages/build..alpha..travis-ci.org)|

#### master branch
- stable branch
- HEAD should be tagged, npm-published package

#### beta branch
- stable branch
- HEAD should be latest, npm-published package

#### alpha branch
- unstable branch
- HEAD is arbitrary
- commit history may be rewritten



# quickstart web example

#### to run this example, follow the instruction in the script below
- example.js

```javascript
/*
example.js

this node script will serve a
lightweight swagger-ui crud-api backed by mongodb

instruction
    1. save this script as example.js
    2. run the shell command:
          $ npm install swagger-mongodb && \
              npm_config_server_port=1337 node example.js
    3. open a browser to http://localhost:1337
    4. interact with the swagger-ui crud-api
*/

/*jslint
    browser: true,
    maxerr: 8,
    maxlen: 96,
    node: true,
    nomen: true,
    stupid: true
*/

(function () {
    'use strict';
    // run node js-env code
    (function () {
        var local;
        // init local
        local = {};
        local.global = global;
        local.modeJs = 'node';
        try {
            local.swmg = require('swagger-mongodb');
        } catch (errorCaught) {
            local.swmg = require('./index.js');
        }
        local.utility2 = local.swmg.local.utility2;
        // init onReady
        local.utility2.onReadyInit();
        // import swmg.local
        Object.keys(local.swmg.local).forEach(function (key) {
            local[key] = local[key] || local.swmg.local[key];
        });
        // export local
        module.exports = local;
        // init assets
        local.utility2.cacheDict.assets['/'] = '<!DOCTYPE html>\n' +
/* jslint-ignore-begin */
'<html>\n' +
'<head>\n' +
'    <meta charset="UTF-8">\n' +
'    <title>\n' +
'    {{envDict.npm_package_name}} [{{envDict.npm_package_version}}]\n' +
'    </title>\n' +
'    <link rel="stylesheet" href="/assets/utility2.css">\n' +
'    <style>\n' +
'    * {\n' +
'        box-sizing: border-box;\n' +
'    }\n' +
'    body {\n' +
'        background-color: #fff;\n' +
'        font-family: Helvetical Neue, Helvetica, Arial, sans-serif;\n' +
'    }\n' +
'    body > div {\n' +
'        margin: 20px 0 20px 0;\n' +
'    }\n' +
'    .testReportDiv {\n' +
'        display: none;\n' +
'    }\n' +
'    </style>\n' +
'    {{envDict.npm_config_html_head_extra}}\n' +
'</head>\n' +
'<body>\n' +
'    <div class="ajaxProgressDiv" style="display: none;">\n' +
'    <div class="ajaxProgressBarDiv ajaxProgressBarDivLoading" \
>loading</div>\n' +
'    </div>\n' +
'    <h1 \
>{{envDict.npm_package_name}} [{{envDict.npm_package_version}}]</h1>\n' +
'    <h3>{{envDict.npm_package_description}}</h3>\n' +
'    <div class="testReportDiv"></div>\n' +
'    <div id="swagger-ui-container" style="display: none;"></div>\n' +
'    <iframe \
height="512" \
src="/assets/swagger-ui.html" \
width="100%" \
></iframe>\n' +
'    <script src="/assets/utility2.js"></script>\n' +
'    <script src="/assets/swagger-ui.rollup.js"></script>\n' +
'    <script src="/assets/swagger-mongodb.js"></script>\n' +
'    <script src="/test/test.js"></script>\n' +
'    <script>\n' +
'    window.utility2 = window.utility2 || {};\n' +
'    window.utility2.envDict = {\n' +
'        npm_package_description: "{{envDict.npm_package_description}}",\n' +
'        npm_package_name: "{{envDict.npm_package_name}}",\n' +
'        npm_package_version: "{{envDict.npm_package_version}}"\n' +
'    };\n' +
'    document.querySelector("iframe").onload = function () {\n' +
'        var self;\n' +
'        self = this;\n' +
'        self.height = innerHeight - self.offsetTop - 20;\n' +
'        self.contentWindow.location.hash = location.hash;\n' +
'        self.contentWindow.onclick = function () {\n' +
'            setTimeout(function () {\n' +
'                location.hash = self.contentWindow.location.hash;\n' +
'            });\n' +
'        };\n' +
'    };\n' +
'    </script>\n' +
'    {{envDict.npm_config_html_body_extra}}\n' +
'</body>\n' +
/* jslint-ignore-end */
            '</html>\n';
        local.utility2.cacheDict.assets['/'] = local.utility2.stringFormat(
            local.utility2.cacheDict.assets['/'],
            { envDict: local.utility2.envDict },
            ''
        );
        local.utility2.cacheDict.assets['/test/test.js'] =
            local.utility2.istanbul_lite.instrumentInPackage(
                local.fs.readFileSync(local.swmg.__dirname + '/test.js', 'utf8'),
                local.swmg.__dirname + '/test.js',
                'swagger-mongodb'
            );
        // init mongodb-client
        local.utility2.onReady.counter += 1;
        local.utility2.taskRunOrSubscribe({
            key: 'swagger-mongodb.mongodbConnect',
            onTask: function (onError) {
                local.mongodb.MongoClient.connect(
                    local.utility2.envDict.npm_config_mongodb_url ||
                        'mongodb://localhost:27017/test',
                    function (error, db) {
                            // validate no error occurred
                            local.utility2.assert(!error, error);
                            local.swmg.db = db;
                            onError();
                            local.utility2.onReady();
                        }
                );
            }
        });
        // init middleware
        local.middleware = local.utility2.middlewareGroupCreate([
            local.utility2.middlewareInit,
            local.utility2.middlewareAssetsCached,
            local.swmg.middleware
        ]);
        // init middleware error-handler
        local.onMiddlewareError = local.swmg.onMiddlewareError;
        // init petstore-api
        (function () {
            var methodPath, options, schema;
            options = local.utility2.jsonCopy(require(local.swmg.local
                .swagger_ui_lite.__dirname + '/swagger.json'));
            options = {
                definitions: options.definitions,
                paths: options.paths,
                tags: options.tags
            };
            Object.keys(options.definitions).forEach(function (schemaName) {
                schema = options.definitions[schemaName];
                schema._collectionName = 'Swmg' + schemaName + 'Collection';
                schema.properties.id = { type: 'string' };
                schema['x-inheritList'] =
                    [{ $ref: '#/definitions/JsonApiResource' }];
            });
            Object.keys(options.paths).forEach(function (path) {
                Object.keys(options.paths[path]).forEach(function (method) {
                    methodPath = options.paths[path][method];
                    methodPath._schemaName =
                        path.split('/')[1][0].toUpperCase() +
                        path.split('/')[1].slice(1);
                    if (methodPath._schemaName === 'Store') {
                        methodPath._schemaName = 'Order';
                    }
                    methodPath._collectionName =
                        'Swmg' + methodPath._schemaName + 'Collection';
                    methodPath.produces =
                        methodPath.responses =
                        methodPath.security =
                        undefined;
                    switch (methodPath.operationId) {
                    case 'addPet':
                    case 'createUser':
                    case 'placeOrder':
                        methodPath._crudApi = true;
                        methodPath.operationId = 'crudCreateOne';
                        break;
                    case 'deleteOrder':
                    case 'deletePet':
                    case 'deleteUser':
                        methodPath._crudApi = true;
                        methodPath.operationId = 'crudDeleteByIdOne';
                        break;
                    case 'getPetById':
                    case 'getOrderById':
                    case 'getUserByName':
                        methodPath._crudApi = true;
                        methodPath.operationId = 'crudGetByIdOne';
                        break;
                    case 'updatePet':
                    case 'updateUser':
                        methodPath._crudApi = true;
                        methodPath.operationId = 'crudUpdateOne';
                        break;
                    }
                    // init id
                    methodPath.parameters.forEach(function (param) {
                        switch (param.name) {
                        case 'orderId':
                        case 'petId':
                        case 'username':
                            methodPath._paramExtraDict = { id: '{{' + param.name + '}}' };
                            param.format = undefined;
                            param.type = 'string';
                            break;
                        }
                    });
                });
            });
            local.swmg.apiUpdate(options);
        }());
        // init petstore-middleware
        local.middleware.middlewareList.push(function (request, response, nextMiddleware) {
            var modeNext, onNext;
            modeNext = 0;
            onNext = function (error, data) {
                local.utility2.testTryCatch(function () {
                    modeNext = error
                        ? Infinity
                        : modeNext + 1;
                    switch (modeNext) {
                    case 1:
                        switch (request.swmgPathname) {
                        case 'GET /pet/findByStatus':
                            local.swmg._crudApi({
                                collectionName: request.swmgMethodPath._collectionName,
                                data: {
                                    fields: '{}',
                                    hint: '{}',
                                    limit: 20,
                                    query: JSON.stringify({
                                        status: { $in: request.swmgParameters.status }
                                    }),
                                    skip: 0,
                                    sort: '{"_timeModified":-1}'
                                },
                                operationId: 'crudGetByQueryMany',
                                parameters: [],
                                schemaName: 'Pet'
                            }, onNext);
                            return;
                        case 'GET /pet/findByTags':
                            local.swmg._crudApi({
                                collectionName: request.swmgMethodPath._collectionName,
                                data: {
                                    fields: '{}',
                                    hint: '{}',
                                    limit: 10,
                                    query: JSON.stringify({
                                        'tags.name': { $in: request.swmgParameters.tags }
                                    }),
                                    skip: 0,
                                    sort: '{"_timeModified":-1}'
                                },
                                operationId: 'crudGetByQueryMany',
                                parameters: [],
                                schemaName: 'Pet'
                            }, onNext);
                            return;
                        }
                        break;
                    default:
                        response.end(JSON.stringify(error || data));
                        return;
                    }
                    nextMiddleware();
                }, nextMiddleware);
            };
            onNext();
        });
        // run server-test
        local.utility2.testRunServer(local);
    }());
}());
```

#### output from shell
[![screen-capture](https://kaizhu256.github.io/node-swagger-mongodb/build/screen-capture.testExampleJs.png)](https://travis-ci.org/kaizhu256/node-swagger-mongodb)

#### output from phantomjs-lite
[![heroku.com test-server](https://kaizhu256.github.io/node-swagger-mongodb/build/screen-capture.testExampleJs.slimerjs..png)](https://hrku01-swagger-mongodb-beta.herokuapp.com)



# npm-dependencies
- [mongodb](https://www.npmjs.com/package/mongodb)
- [swagger-ui-lite](https://www.npmjs.com/package/swagger-ui-lite)
- [utility2](https://www.npmjs.com/package/utility2)



# package-listing
[![screen-capture](https://kaizhu256.github.io/node-swagger-mongodb/build/screen-capture.gitLsTree.png)](https://github.com/kaizhu256/node-swagger-mongodb)



# package.json
```json
{
    "author": "kai zhu <kaizhu256@gmail.com>",
    "bin": { "swagger-mongodb": "index.js" },
    "dependencies": {
        "mongodb-minimal": "^2015.6.1",
        "swagger-ui-lite": "^2015.6.1",
        "utility2": "~2015.7.1"
    },
    "description": "lightweight swagger-ui crud-api backed by mongodb",
    "devDependencies": {
        "phantomjs-lite": "^2015.6.1"
    },
    "engines": { "node": ">=0.10 <=0.12" },
    "keywords": [
        "api",
        "browser",
        "cms", "crud",
        "mongo", "mongodb",
        "swagger", "swagger-ui",
        "web"
    ],
    "license": "MIT",
    "name": "swagger-mongodb",
    "os": ["darwin", "linux"],
    "repository" : {
        "type" : "git",
        "url" : "https://github.com/kaizhu256/node-swagger-mongodb.git"
    },
    "scripts": {
        "build-ci": "node_modules/.bin/utility2 shRun shReadmeBuild",
        "postinstall": \
"node_modules/.bin/utility2 shRun shReadmeExportFile example.js example.js",
        "start": "npm_config_mode_auto_restart=1 \
node_modules/.bin/utility2 shRun node test.js",
        "test": "node_modules/.bin/utility2 shRun shReadmeExportPackageJson && \
node_modules/.bin/utility2 test test.js"
    },
    "version": "2015.7.2"
}
```



# todo
- add aggregation feature
- add max / min validation
- add createIndex feature to apiUpdate
- add aggregate crud api
- add user /login /logout paths
- cap test collections
- add formData swagger parameter type
- none



# change since a90c3c40
- npm publish 2015.7.2
- auto-export example.js in test.js
- replace utility2.streamReadAll with utility2.middlewareBodyGet for parsing http-body
- add collectionFormat option for csv array
- revamp petstore-api
- none



# changelog of last 50 commits
[![screen-capture](https://kaizhu256.github.io/node-swagger-mongodb/build/screen-capture.gitLog.png)](https://github.com/kaizhu256/node-swagger-mongodb/commits)



# internal build-script
- build.sh

```shell
# build.sh

# this shell script will run the build for this package

shBuild() {
    # this function will run the main build
    # init env
    export npm_config_mode_slimerjs=1 || return $?
    . node_modules/.bin/utility2 && shInit || return $?

    # run npm-test on published package
    shNpmTestPublished || return $?

    # test example js script
    export npm_config_timeout_exit=10000 || return $?
    MODE_BUILD=testExampleJs \
        shRunScreenCapture shReadmeTestJs example.js || return $?
    unset npm_config_timeout_exit || return $?

    # run npm-test
    MODE_BUILD=npmTest shRunScreenCapture npm test || return $?

    # if running legacy-node, then do not continue
    [ "$(node --version)" \< "v0.12" ] && return

    # deploy app to heroku
    shHerokuDeploy hrku01-$npm_package_name-$CI_BRANCH || return $?

    # test deployed app to heroku
    if [ "$CI_BRANCH" = alpha ] ||
        [ "$CI_BRANCH" = beta ] ||
        [ "$CI_BRANCH" = master ]
    then
        TEST_URL="https://hrku01-$npm_package_name-$CI_BRANCH.herokuapp.com" \
            || return $?
        TEST_URL="$TEST_URL?modeTest=phantom&timeExit={{timeExit}}" || return $?
        MODE_BUILD=herokuTest shPhantomTest "$TEST_URL" || return $?
    fi
}
shBuild

# save exit-code
EXIT_CODE=$?

shBuildCleanup() {
    # this function will cleanup build-artifacts in local build dir
    # create package-listing
    MODE_BUILD=gitLsTree shRunScreenCapture shGitLsTree || return $?
    # create recent changelog of last 50 commits
    MODE_BUILD=gitLog shRunScreenCapture git log -50 --pretty="%ai\u000a%B" || \
        return $?
}
shBuildCleanup || exit $?

shBuildGithubUploadCleanup() {
    # this function will cleanup build-artifacts in local gh-pages repo
    return
}

# if running legacy-node, then do not continue
[ "$(node --version)" \< "v0.12" ] && exit $EXIT_CODE

# upload build-artifacts to github,
# and if number of commits > 16, then squash older commits
COMMIT_LIMIT=16 shBuildGithubUpload || exit $?

# exit with $EXIT_CODE
exit $EXIT_CODE
```
