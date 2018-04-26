![Tramel Woodard](http://tramelwoodard.com/images/global/tlw_icon.png "Tramel Woodard")
# Angular 5 Demo
Demo of Angular 5 for Educational Purposes.

This repository is an Angular 5 implementation of Angular Tour of Heroes.

## Angular 5 Issues that Needed Resolving

#### Generating a New Component
After generating a new project using @angular/cli, generating a new component:

```
ng generate component NewComponent
```

or

```
ng g c NewComponent
```

produces the following Command Line Interface error:

```
core_1.PriorityQueue is not a constructor
TypeError: core_1.PriorityQueue is not a constructor
```

Although there may be several ways to fix this issue, I do not use Angular 2/4/5 at work and therefore fell behind in my @angular/cli version at home. I simply updated my global version of Angular using the Command Line Interface with the following commands:

```
npm remove -g @angular/cli
npm install -g @angular/cli@latest
```

which did the trick.

#### HttpClient / In-Memory-Data API Error
When creating a Angular Tour of Heroes application from the official Angular 5.2.6 documentation, the completed page that calls the API returns a 404 error. This is due to a version mismatch. 

```
"angular-in-memory-web-api": "^0.3.1"
```

to the following:

```
"angular-in-memory-web-api": "^0.5.0"
```

This of course requires the Module name and location of import to be changed. The pull request to fix this still hasn't been accepted by the official Github page, however here is a link to the open pull request, to see all of the changes that were required and also modified in my Angular 5.2.6 demo:

[update to angular-in-memory-web-api 0.5.0 and httpClient](https://github.com/johnpapa/angular-tour-of-heroes/pull/135/files)

