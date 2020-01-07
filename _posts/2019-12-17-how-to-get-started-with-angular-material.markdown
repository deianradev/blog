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

If you're using Hammer.js and you've started your project with Angular CLI, then you need to modify the angular-cli.json file and add the Hammer.js library. You do this in the ```"scripts"``` array and add the following path:

```
"scripts": [
  "../node_modules/hammerjs/hammer.min.js"
],
```

Remember, you may need to restart your local server in order for the changes to take effect.

## Step 2: Add Angular Material to app module file

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
