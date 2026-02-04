# Week 1 - Typescript

Topics:

    * Introduction
    * Environment Set Up
    * Linked List

## I. Introduction

>TypeScript is a very useful and powerful tool we can use to optimize our code by checking for syntax errors before runtime, giving tips on how to fix bugs before they happen and more, all by adding in types to our regular JavaScript code! 

>Though we can start using TypeScript right out of the box, it does recognize that every application and developer is different, and gives us some room for flexibility. 

>We get access to this flexibility/customization through the ts.config file that we will keep in the root of our application, where we can change default rules, and add some rules of our own!
><p style="text-align: right;">-Armaan on notion</p>

### Typescript property
* TypeScript is a **static type checker** (TypeScript checks your code before you run it)
* TypeScript is a **superset of JavaScript** (this means that any JavaScript program is also a valid TypeScript program)
* TypeScript **preserves the runtime behavior of JavaScript** (TypeScript doesn’t change how JavaScript works)
* TypesScript **compiles to JavaScript**
* **Types are gone once it compiles to JavaScript** (the browser and **Node** don’t understand TypeScript)
* Using TypeScript is a **gradual adoption**

## II. Environment Set Up

### Download

npm install -g typescript 

### tsconfig.json


The tsconfig file is used to help us configure and compile our code

This file is always kept in the project's root, and is used to identify the compiler rules the user wants to enforce, as well as specify the root files of the project. The rules the compiler enforces are customizable based on project needs.

To get configuration file (tsconfig.json) : tsc --init

### Compiling with tsc

With tsconfig.json set up, tsc commands are available for compiling codes.  
Runs "tsc [specific file name]".

When we run tsc, our program takes our .ts files and compiles them into JavaScript code, or .js files. This command not only creates our .js files in the same directory as our .ts files, but also is how we are able to see the errors and bugs that the transpiler has found, allowing us to fix them immediately.

## III. Why Bother Using Typescript?

Because when js was first designed it aimed to be forgiving when it comes to mistakes, When writing JavaScript we don’t get a lot of information before we run our code.

There’s no way for us to know if the JavaScript code has errors until we see the result on the page and go back to our code editor to fix the mistake and rerun the code.

TypeScript helps you catch mistakes early, before your code runs.

### Type in Typescript

Javascript has something called implicit coercion where js sees different types of data interact with each other but doesn't return an error, instead it assumes  what the programmer want and automatically convert a data type to match. 

Implicit often does more harm than good. To avoid said problem, typescript requires you to state the data type clearly. Typescript acts as a body guard for your code. If the incoming types don't match, they cannot enter the function.

Specificly, 
Typescript a
