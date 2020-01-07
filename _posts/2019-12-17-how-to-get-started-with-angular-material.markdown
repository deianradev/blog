---
layout: post
title: "How to get started with Angular Material"
date: 2019-12-17 13:32:20 +0300
description: A basic guid to getting started with Angular Material
img:  # Add image post (optional)
---

## Why Use Angular Material
* Integrates well with Angular framework
* Well supported by Angular team

## Step 1: Install dependencies
```
npm install --save @angular/material @angular/animations @angular/cdk
```
```
npm install --save hammerjs
```
Hammer.js is optional, but it helps with touch support for a few components. It's mostly for mobile support of the webpage

If you're not using Hammer.js, you can ignore the rest of this step.
If you're using Hammer.js and you've started your project with Angular CLI, then you need to modify the angular-cli.json file and add the Hammer.js library. You do this in the ```"scripts"``` array and add the following path:

```
"scripts": [
  "../node_modules/hammerjs/hammer.min.js"
],
```

Remember, you may need to restart your local server in order for the changes to take effect.

## Step 2: Create a custom material module
This is where you import all the components you need. You will then import this in the app.module.ts file
```
import { NgModule } from '@angular/core';

import {
  MatButtonModule,
  MatMenuModule,
  MatToolbarModule,
  MatIconModule,
  MatCardModule
} from '@angular/material';

@NgModule({
  imports: [
    MatButtonModule,
    MatMenuModule,
    MatToolbarModule,
    MatIconModule,
    MatCardModule
  ],
  exports: [
    MatButtonModule,
    MatMenuModule,
    MatToolbarModule,
    MatIconModule,
    MatCardModule
  ]
})
export class MaterialModule {}
```
## Step 3: Add Angular Material to app module file

```js
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { FormsModule } from '@angular/forms';
import { HttpModule } from '@angular/http';
import { MaterialModule } from './material.module';
import { BrowserAnimationsModule } from '@angular/platform-browser/animations';

import { AppComponent } from './app.component';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    FormsModule,
    HttpModule,
    MaterialModule,
    BrowserAnimationsModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

## Step 4: Import a pre-build Material theme and icons
In you styles.css you can include the following line:
```@import '~@angular/material/prebuilt-themes/indigo-pink.css';```

You can also have access to the Material Design icons and use named icons with the <mat-icon> component. To import them to your project, you can add this to the head section of your project’s root index.html file:
You can also import the icons in your index.html file
```<link rel="stylesheet" href="https://fonts.googleapis.com/icon?family=Material+Icons">```

## Step 5: Test it out
Create a html page and test out our newly installed Angular Material
<div>
  <mat-toolbar color="primary">
    <span><mat-icon>mood</mat-icon></span>

    <span>Yay, Material in Angular 2!</span>

    <button mat-icon-button [mat-menu-trigger-for]="menu">
      <mat-icon>more_vert</mat-icon>
    </button>
  </mat-toolbar>
  <mat-menu x-position="before" #menu="matMenu">
    <button mat-menu-item>Option 1</button>
    <button mat-menu-item>Option 2</button>
  </mat-menu>

  <mat-card>
    <button mat-button>All</button>
    <button mat-raised-button>Of</button>
    <button mat-raised-button color="primary">The</button>
    <button mat-raised-button color="accent">Buttons</button>
  </mat-card>

  <span class="done">
    <button mat-fab>
      <mat-icon>check circle</mat-icon>
    </button>
  </span>
</div>
