# Angular-CLI

## What is angular-cli ?

Angular-CLI is a Command Line Interface tool that creates and scaffolds an Angular 2 application for you. The application comes with a built-in development server, TypeScript 2 support, unit- and End-to-End testing, etc... Angular-CLI has been introduced at ng-conf 2016 and it is still in beta for now.

## History

Foremost was the incredibly slow app refresh during development due to SystemJS loading every file dynamically —definitely a deal breaker.
All the gains made with scaffolding efficiency were quickly offset by the painfully slow app refreshes and the 5 step process to add 3rd party npm modules. So I backburnered it in favor of Angular 2 Webpack seeds.


## Old technologies ...

* Amber-cli with SystemJS

** Dynamically loading every file

** No css reload

### Ember CLI
Ember CLI is a Command Line Interface from EmberJS that gives you a powerful tool to generate a project structure, an asset pipeline and an addon system for extension. The addon system creates reusable units of code. It uses babel to convert ES6 module syntax into AMD modules. Ember CLI is continuously evolving. It’s an on-going community effort.

Angular-CLI is based on Ember-CLI but focuses on creating a ready to use webapp with Angular 2.

### SystemJS
SystemJS is a module loader. It features plugins which can be used to process CSS, HTML, SASS, etc... SystemJS relies on Promises, so it is advisable to load Bluebird or es6-promise before loading SystemJS.

## ... to new technologies

## Pros now

* Better reload -> building sass/scss/less -> css -> reload

* Tree Shaking
The last major feature the Webpack angular-cli brings is Tree-Shaking. This is a process that scours your entire project and prevents any unreferenced code from being included in the bundle. This significantly reduces the bundle size. In the case of our demo app, the bundle size is cut by nearly 1/3!!

* Generators

### Webpack
Webpack is a module bundler. It takes modules with dependencies and generates static assets representing those modules. Those assets can be loaded in the browser to generate your web application.
Webpack stable release was introduced in the beginning of 2014. During the last two years, more features have been added to Webpack and it has been actively maintained.
Currently, version 2 is in beta with a lot of improvements for ES6. For example, it brings native support for ES6 Modules, which means you won't have to transform the import and export statements anymore with CommonJS. Not depending on CommonJS enables Tree shaking in Webpack 2, as CommonJS exports leaves references alive so they would be included in the final build.

Angular-CLI's build system has been updated from SystemJS to Webpack. This brings in a lot of improvements for the tool. It requires less time spent into configuration. The building process has been improved, so it runs faster.

## Generators
theory


## Future:
Webpack has another feature that supercharges iteration speeds; Hot Module Reload (aka HMR). HMR hot-reloads only the parts of the application that have changed without refreshing the browser. Although HMR is not available in this version of angular-cli, there is talk of adding HMR to a future release. In the meantime, Patrick at AngularClass has created a library that integrates HMR with Angular 2 if curiosity strikes you.


## How to:
* ng new {yourProject}
* ng serve
* ng build
* ng test
* ng e2e
* and of course 'fun with flags' (--target --environment )  //sheldon cooper

### ng new ordinaJworks

--style=sass // scss/less/style

or you can set it later

```
$ ng set defaults.styleExt scss
```


or manual by adjusting the `angular-cli.json'

```
"defaults": {
    "styleExt": "scss",
    "prefixInterfaces": false
 }
```

```
"apps": [
    {
      ...
      "styles": [
        "styles.scss"
      ],
      ...
  ],
```

and of course renaming the file(s) from the current to the new format and the references to it.


#### scafholding
-> structure
-> config files
->
-> unit testing
-> e2e testing

#### Git ready

#### test ready

#### Comes with one main component and a main NgModule


### ng serve

### ng build

### ng test

### ng e2e

### Flags

Environmental setting.
angular-cli.json
"environments": {
  "source": "environments/environment.ts",
  "dev": "environments/environment.ts",
  "prod": "environments/environment.prod.ts"
}




## Creation of a project
