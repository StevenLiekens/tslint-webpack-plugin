# tslint-webpack-plugin

[![npm version](https://badge.fury.io/js/tslint-webpack-plugin.svg)](http://badge.fury.io/js/html-webpack-plugin)
[![license](https://img.shields.io/github/license/mashape/apistatus.svg?maxAge=2592000)]()

[![NPM](https://nodei.co/npm/tslint-webpack-plugin.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/html-webpack-plugin/)

This is a [webpack](http://webpack.github.io/) plugin that provides a very simple method of running TSLint alongside your webpack builds.
This project differs from [tslint-loader](https://github.com/wbuchwalter/tslint-loader) in that it will lint all specified files rather that only
those that are imported by webpack. This is espcially useful for interface files that are not always picked up by webpack (due to treeshaking or whatever).

Installation
------------
This plugin also requires [TSLint](https://github.com/palantir/tslint) to be installed.

Install the plugin with npm:
```shell
$ npm install tslint tslint-webpack-plugin --save-dev
```

Basic Usage
-----------

The plugin will output tslint errors as part of your webpack build process. It will not fail the build, but simply notify you of changes that need to be made.
Just add the plugin to your webpack config as follows:

```javascript
var TSLintPlugin = require('tslint-webpack-plugin');
var webpackConfig = {
  entry: 'index.js',
  output: {
    path: 'dist',
    filename: 'index_bundle.js'
  },
  plugins: [
    new TSLintPlugin({
      files: ['./src/**/*.ts']
    })
  ]
};
```

Configuration
-------------
You can pass a hash of configuration options to `TSLintWebpackPlugin`.
Allowed values are as follows:

- `files`: `string | string[]` The files to run through the linter.
  - Examples
    - `'./src/**/*.ts'`
    - `['./src/**/*.ts', './test/**/*.spec.ts']`
    - `'./src/main.ts'`
    - `['./src/main.ts', './test/main.spec.ts']`


# License

This project is licensed under [MIT](https://github.com/ampedandwired/html-webpack-plugin/blob/master/LICENSE).
