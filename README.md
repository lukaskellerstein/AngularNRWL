This repo showed howto use NRWL in Angular 6 projects




# DELETE

# Notes

myapp1 = using NgRX and dispatch action from one libraries in the other one.


# Install necessary libraries

NPM

`npm install -g @angular/cli`
`npm install -g @nrwl/schematics`
`npm install -g @ngrx/schematics`

or better approach is use a YARN

`yarn global add @angular/cli`
`yarn global add @nrwl/schematics`
`yarn global add @ngrx/schematics`


# Generate Solution

Create solution

`ng new TestSolution --collection=@nrwl/schematics`

## Create Application

`ng g app myapp-admin --style=scss`
`ng g app myapp-web --style=scss`

## Create Common library

Common library will constist of LoginPage, ErrorPage, NotFoundPage ... etc.

`ng g lib common`


## Create Widgets library

Widgets library is SHARED library for each feature module.

`ng g lib widgets`


## Create Feature libs / Feature modules

Business related modules / libs. For each feature module create this folder structure.

1. +State
- NgRx Store

2. Components
- Dumb Components - use @Input and @Output, doesn't know anything about services and state.

3. Containers
- Smart Components - wrapper for Dumb components, know everything about services and state.

4. Directives
- Angular custom directives

5. Pipes
- Angular custom pipes

6. Services
- Angular custom services

7. Entities
- Custom classes / types / entities


### Cafe Management

`ng g lib cafeManagement`

Add State
`ng generate ngrx cafe-management --module=libs/cafe-management/src/lib/cafe-management.module.ts`



### Products Management

`ng g lib productsManagement`

Add State
`ng generate ngrx products-management --module=libs/products-management/src/lib/products-management.module.ts`


### Trainings Management

`ng g lib trainigsManagement`

Add State
`ng generate ngrx trainings-management --module=libs/trainings-management/src/lib/trainings-management.module.ts`



## Add NgRX

Root state
`ng generate ngrx app --module=apps/myapp1/src/app/app.module.ts  --root`

Feature state
`ng generate ngrx mylib1 --module=libs/mylib1/src/lib/mylib1.module.ts`


# RUN 

you can run every app independently

`ng serve --project=myapp1`