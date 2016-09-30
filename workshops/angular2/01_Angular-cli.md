# Angular-CLI

## What is angular-cli ?

## History

Foremost was the incredibly slow app refresh during development due to SystemJS loading every file dynamically —definitely a deal breaker.
All the gains made with scaffolding efficiency were quickly offset by the painfully slow app refreshes and the 5 step process to add 3rd party npm modules. So I backburnered it in favor of Angular 2 Webpack seeds.



## Old technologies ...

* Amber-cli with SystemJS

** Dynamically loading every file

** No css reload

## ... to new technologies

## Pros now

* Better reload -> building sass/scss/less -> css -> reload

* Tree Shaking
The last major feature the Webpack angular-cli brings is Tree-Shaking. This is a process that scours your entire project and prevents any unreferenced code from being included in the bundle. This significantly reduces the bundle size. In the case of our demo app, the bundle size is cut by nearly 1/3!!

* Generators

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
