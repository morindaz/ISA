# ISA management webapp
### you need
1. nodejs
2. mongodb

### after clone the project you need run
1. npm install
2. bower install

# Usage

## Create your project

## Yo options
`yo gulp-angular --help` or `yo gulp-angular -h` for help. All options are not required. If not provided, default values will be used.

* `--app-path='src'` customize Angular's app folder, relative to cwd, default is `src`
* `--dist-path='dist'` customize build target folder, relative to cwd, default is `dist`
* `--e2e-path='e2e'` customize e2e test specs folder, relative to cwd, default is `e2e`
* `--tmp-path='.tmp'` customize pre-processing temp folder, relative to cwd, default is `.tmp`
* `--skip-install` do not run `bower install` and `npm install` after generating the app, default is `false` (not skip)
* `--skip-welcome-message` skip yo welcome messages, default is `false` (not skip)
* `--skip-message` skip install messages, default is `false` (not skip)
* `--default` use default configurations, default is `false`
* `--advanced` prompt for advanced additional features, default is `false`

Paths configuration are stored in `gulpfile.js`. Change `options.(src|dist|tmp|e2e)` in `gulpfile.js` if you want to config paths after the app is generated.

**Warning**: The paths are also written in the `index.html` for the build with useref. If you want to change these paths, you also have to change the paths there in order to have the build task working.

## Use Gulp tasks

* `gulp` or `gulp build` to build an optimized version of your application in `/dist`
* `gulp serve` to launch a browser sync server on your source files
* `gulp serve:dist` to launch a server on your optimized application
* `gulp test` to launch your unit tests with Karma
* `gulp test:auto` to launch your unit tests with Karma in watch mode
* `gulp protractor` to launch your e2e tests with Protractor
* `gulp protractor:dist` to launch your e2e tests with Protractor on the dist files

More information on the gulp tasks in the [User Guide](user-guide.md).

## Directory structure

[Best Practice Recommendations for Angular App Structure](https://docs.google.com/document/d/1XXMvReO8-Awi1EZXAXS4PzDzdNvV6pGcuaF4Q9821Es/pub)

The root directory generated with default paths configuration for application with name `gulpAngular`:
<pre>
├──  bower_components/
├──  e2e/
├──  gulp/
├──  nodes_modules/
│
├──  src/
│   ├──  app/
│   │   ├──  components/
│   │   │   └──  githubContributor/
│   │   │   │   └──  githubContributor.service.js
│   │   │   │
│   │   │   └──  malarkey/
│   │   │   │   ├──  malarkey.directive.js
│   │   │   │   └──  malarkey.(scss|styl|less|css)
│   │   │   │
│   │   │   └──  navbar/
│   │   │   │   ├──  navbar.directive.(js|ts|coffee)
│   │   │   │   ├──  navbar.html
│   │   │   │   └──  navbar.(scss|styl|less|css)
│   │   │   │
│   │   │   └──  webDevTec/
│   │   │       └──  webDevTec.service.js
│   │   │
│   │   ├──  main/
│   │   │   ├──  main.controller.(js|ts|coffee)
│   │   │   ├──  main.controller.spec.js
│   │   │   └──  main.html
│   │   │
│   │   └──  index.config.(js|ts|coffee)
│   │   └──  index.constants.(js|ts|coffee)
│   │   └──  index.module.(js|ts|coffee)
│   │   └──  index.route.(js|ts|coffee)
│   │   └──  index.run.(js|ts|coffee)
│   │   └──  index.(scss|styl|less|css)
|   |
│   ├──  assets/
│   │   └──  images/
│   ├──  favico.ico
│   └──  index.html
│
├──  .bowerrc
├──  .editorconfig
├──  .gitignore
├──  .eslintrc
├──  bower.json
├──  gulpfile.js
├──  karma.conf.js
├──  package.json
└──  protractor.conf.js
</pre>

There is none at the generation but you can add `.jade`, `.haml` or `.hbs` (dependent of your HTML pre-processor choice) anywhere in the `src` folder and it will be compiled automatically. **Warning**, the first file of a type in a folder is often missed by the Gulp watch, try to relaunch Gulp if it happens.


## Features included in the gulpfile
* *useref* : allow configuration of your files in comments of your HTML file
* *ngAnnotate* : convert simple injection to complete syntax to be minification proof
* *uglify* : optimize all your JavaScript
* *csso* : optimize all your CSS
* *autoprefixer* : add vendor prefixes to CSS
* *rev* : add a hash in the file names to prevent browser cache problems
* *watch* : watch your source files and recompile them automatically
* *eslint* : The pluggable linting utility for JavaScript
* *imagemin* : all your images will be optimized at build
* *Unit test (karma)* : out of the box unit test configuration with karma
* *e2e test (protractor)* : out of the box e2e test configuration with protractor
* *browser sync* : full-featured development web server with livereload and devices sync
* *angular-templatecache* : all HTML partials will be converted to JS to be bundled in the application
* **TODO** lazy : don't process files which haven't changed when possible


## Questions the generator will ask
* *jQuery*: jQuery 1.x, 2.x, Zepto, none
* *Angular modules*: animate, cookies, touch, sanitize
* *Resource handler*: ngResource, Restangular, none
* *Router*: ngRoute, UI Router, none
* *UI Framework*: Bootstrap, Foundation, Angular Material, Material Design Lite, none (depends on the chosen CSS preprocessor)
* *UI directives* : UI Bootstrap, Angular Strap, official Bootstrap JavaScript, Angular Foundation, official Foundation JavaScript, none (depends on the UI framework)
* *CSS pre-processor*: Less, Sass with Ruby and Node, Stylus, none
* *JS preprocessor*: CoffeeScript, TypeScript, ECMAScript 6 (Traceur and Babel), none
* *HTML preprocessor*: Jade, Haml, Handlebars, none
* **TODO** Script loader: Require, Webpack, none
* **TODO** Test framework: Jasmine, Mocha, Qunit


<!-- # generator-gulp-angular ![Logo](generators/app/templates/src/assets/images/generator-gulp-angular-logo.png)

[![Unmaintained](https://img.shields.io/badge/generator-unmaintained-red.svg?style=flat-square)](https://github.com/Swiip/generator-gulp-angular/pull/1155)
[![Outdated](https://img.shields.io/badge/generator-outdated-red.svg?style=flat-square)](https://github.com/Swiip/generator-gulp-angular/pull/1155)

[![Build Status](https://img.shields.io/travis/Swiip/generator-gulp-angular/master.svg?style=flat-square)](http://travis-ci.org/Swiip/generator-gulp-angular)
[![Coverage Status](https://img.shields.io/codecov/c/github/Swiip/generator-gulp-angular.svg?style=flat-square)](http://codecov.io/github/Swiip/generator-gulp-angular?branch=master)
[![Dependencies](http://img.shields.io/david/Swiip/generator-gulp-angular.svg?style=flat-square)](https://david-dm.org/eleven-labs/generator-gulp-angular)
[![NPM Version](http://img.shields.io/npm/v/generator-gulp-angular.svg?style=flat-square)](https://www.npmjs.org/package/generator-gulp-angular)
[![Download Month](http://img.shields.io/npm/dm/generator-gulp-angular.svg?style=flat-square)](https://www.npmjs.org/package/generator-gulp-angular)

> Yeoman generator for AngularJS + Gulp.

> Lets you quickly set up a project with:
> * your favorite technologies
> * web best pratices.
> * guidelines powered by Google.

> Gulp provide fast workspace with quick feedback.

# **Unmaintained**, **Outdated** ? :pensive:
Yup, this generator works but is unmaintained and outdated [for various reasons](https://github.com/Swiip/generator-gulp-angular/pull/1155).

But don't panic **the most important features and more are present** in our next iteration called [FountainJS](http://fountainjs.io/).

<p align="center">
  <a href="http://fountainjs.io/">
    <img alt="FountainJS" src="http://fountainjs.io/assets/imgs/fountain.png" width="200">
  </a>
</p>

A tutorial is present in the [Yeoman codelab](http://yeoman.io/codelab/). :kissing_heart:

## Usage

More informations, options, parameters in the [usage documentation page](docs/usage.md)

### Install

##### Install required tools `yo`, `gulp` and `bower`:
```
npm install -g yo gulp bower
```

##### Install `generator-gulp-angular`:
```
npm install -g generator-gulp-angular
```


### Run

##### Create a new directory, and go into:
```
mkdir my-new-project && cd $_
```

##### Run `yo gulp-angular`, and select desired technologies:
```
yo gulp-angular
```

## Documentation

* [docs/README](docs/README.md)
* More informations about how to use your new project is available in the [docs/user-guide](docs/user-guide.md)
* If you want to know: [docs/how-it-works](docs/how-it-works.md).


## Features

![Logo](docs/assets/gulp.png)
![Logo](docs/assets/angular.png)
![Logo](docs/assets/bootstrap.png)
![Logo](docs/assets/materialdesign.png)
![Logo](docs/assets/foundation.png)
![Logo](docs/assets/bower.png)
![Logo](docs/assets/webpack.png)
![Logo](docs/assets/karma.png)
![Logo](docs/assets/istanbul.png)
![Logo](docs/assets/browsersync.png)
![Logo](docs/assets/jasmine.png)
![Logo](docs/assets/protractor.png)

![Logo](docs/assets/babel.png)
![Logo](docs/assets/coffeescript.png)
![Logo](docs/assets/typescript.png)
![Logo](docs/assets/traceur.png)
![Logo](docs/assets/sass.png)
![Logo](docs/assets/less.png)
![Logo](docs/assets/stylus.png)
![Logo](docs/assets/jade.png)
![Logo](docs/assets/haml.png)
![Logo](docs/assets/handlebars.png)

[List features included](docs/usage.md#features-included-in-the-gulpfile)


## Questions the generator will ask

[Questions the generator will ask](docs/usage.md#questions-the-generator-will-ask)


## Changelog

[All changes listed in the GitHub releases](https://github.com/Swiip/generator-gulp-angular/releases)


## Contributing

[Guidelines](CONTRIBUTING.md)


## License

MIT
 -->