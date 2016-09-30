# Angular-CLI

## What is angular-cli ?

## History

## Old technologies ...

## ... to new technologies

## Generators
theory





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
