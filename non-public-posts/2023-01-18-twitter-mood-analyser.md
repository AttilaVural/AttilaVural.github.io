---
layout: post
title:  "Twitter Mood Analyzer using python and Vue.js"
date:   2023-01-18 15:00:00 +0100
categories: Code
mermaid: true
---
Steps: 
0. Create a new folder on your desktop called _Twitter_sentiment_.
1. Follow the steps in my post about setting up a simple bokeh server, and copy the resulting _bokeh_server.py_ file into the _Twitter_sentiment_ folder. [Link til post om at opsætte bokeh server application]
2. Follow the step in my post about setting up a simple python script for scraping Twitter posts using the SNscrape library. Copy the resulting _SNscraper.py_ file into the _Twitter_sentiment folder_.



In this blog post, we will guide you through the process of creating a "Twitter Mood Analyzer" using Vue.js and Python. 
You will learn how to use python and the twitter API for retrieve tweets, using deep learning libraries to perform sentiment analysis, 
and create cool data vizualisations. 
Not only is this project a great way to learn new skills, it's also a fun and unique project to add to your portfolio

Vue.js will be used for building a static Single Page Application (SPA) front-end consisting of static html, css and js files. 
All processing will be done by performing POST API calls to the backend server running python FLASK.

<div class="mermaid">
graph LR
    A[Vue.js static SPA]
    A-- POST request -->B[Python Flask server]
    B-- JSON object -->A
</div>

## Prerequisites
* Python 3.2.2.22.2.2. or newer
* PIP (python package manager)

## 1. fetching tweets - SNscraper and vaderSentiment.
SNscracper - better then tweepy because you don't have to get api login - can scrape more and very simple.
vaderSentiment - more sophisticated than TextBlob for sentiment analysis.

Open up your favorite terminal and create the project folder:
> mkdir twitter_mood

> cd twitter_mood

2. Create a virtual environmens - installating the python packages globally could break system tools or other projects.
> python -m venv env

You will notice that this creates the _env_ directory. Since a virtual environment is "just" this directory, which containing installed libraruesm, binaries and scripts under it, you can remove it the same way you remove any directory.

Activate the virtual environment and install the needed packages:
> .\env\scripts\activate

**Install dependencies**
To interact with twitter API you need to install python twitter library, you can install it by running the command 
> pip install python-twitter in your command prompt.

To perform Sentiment Analysis, you need to install NLTK library which can be installed by running the command 
> pip install nltk 

Remember to export all installed libraries to a text file using the _pip freeze_ command:
> pip freeze > requirements.txt

Now you can exclude the relatively large env folder, from your commits and instead just include your requirements.txt file in your repo. Now when anyone wants to clone this repo, they can simply download the source files, create a fresh virtual environment and recreate your env folder by running:
> pip install -r requirements.txt



3) Run the application
> python bookmanager.py

4) Navigate to localhost:5000 in your browser




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
Assuming you have and up-to-date installation of node.js on your workstation, open up your favorite terminal. Next, type the following to create the Vue.js project with an up-to-date version of Vue.js:
> npm init vue@latest

Enter the Project name, package name, and answer _No_ to all prompts except for _Add Vue Router for Single Page Application development?_ where you should choose _Yes_, since we want to the user to be able to load different pages without refreshing the browser.

Enter your newly created folder:
> cd "Twitter mood analyzer"

Let's install and run the project, just to see what we have so far:
> npm install
> npm run dev

![image](https://user-images.githubusercontent.com/115409427/213210869-5554542c-47cd-440c-a0c2-040808b7e87e.png)

## 2. Install the necessary libraries and dependencies.
Exit the exit the running VITE session in your terminal (ctr + c on Windows).

To install axios, you can use npm by running the following command in the root of your project: 
> npm install axios. 

This will allow you to easily make API requests from your Vue.js components.

To install vue-chartjs, you can use npm by running the command: 
> npm install vue-chartjs chart.js

This library allows you to easily create charts and data visualizations in your Vue.js components.







