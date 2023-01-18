---
layout: post
title:  "Twitter Mood Analyzer using python and Vue.js"
date:   2023-01-18 15:00:00 +0100
categories: jekyll update
---
In this blog post, we will guide you through the process of creating a "Twitter Mood Analyzer" using Vue.js and Python. 
You will learn how to use python and the twitter API for retrieve tweets, using deep learning libraries to perform sentiment analysis, 
and create cool data vizualisations. 
Not only is this project a great way to learn new skills, it's also a fun and unique project to add to your portfolio

## Prerequisites
* Basic knowledge of JavaScript and Vue.js
* Basic knowledge of Python

## Setting up the environment
Vue.js is not built on top of Node.js, but it does require Node.js to be installed in order to use the Vue CLI (Command Line Interface) tool 
and NPM (Node Package Manager), which is used to create and manage Vue.js projects. The Vue CLI tool uses Node.js to run a development server
and build scripts, so you'll need Node.js installed on your computer in order to use it.

Node.js brings with it NPM which is used to manage packages and dependencies for your project. NPM provides a command line interface to
interact with the npm registry, which is a large repository of open-source packages. With Vue.js you will use NPM to install its packages and
dependencies, as well as other packages like axios, vue-chartjs, and others.

Vue.js itself is a JavaScript framework for building user interfaces. It can be used with any web development stack, including Node.js. 
With Node.js and NPM installed you can use it to build a full-stack web application using Vue.js as the front-end framework, and Node.js 
as the back-end runtime environment, or you can use it to build a static front-end web application which can be served by any web server.

** Installing node.js **

## 1- Create a new Vue.js project using the Vue CLI. 
Assuming you have and up-to-date installation of node.js on your workstation, open up your favorite terminal. Next, type the following to to create the Vue.js project with an up-to-date version of Vue.js:
> npm init vue@latest

Enter the Project name, package name, and answer _No_ to all prompts except for _Add Vue Router for Single Page Application development?_ where you should choose _Yes_, since we want to the user to be able to load different pages without refreshing the browser.

Enter 
