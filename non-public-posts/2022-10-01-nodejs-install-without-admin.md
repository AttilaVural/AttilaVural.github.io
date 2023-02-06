---
layout: post
title:  "Instal node.js without admin rights"
date:   2022-10-01 16:00:00 +0000
categories: Code
---
Installing node.js on Windows without admin rights

1. Download the node.js LTS binary for Windows (https://nodejs.org/en/download/) and extract it to your desired location.
2. Add the path of the nodejs folder to the PATH environment variable.
    a. Open the Shortcut winkey+R and enter: "rundll32 sysdm.cpl,EditEnvironmentVariables"
    b. Add the path under your "user variables". You cannot change system variable without admin rights.
3. Open a new command window (winkey+R and type cmd)
4. Type node -v and npm -v to verify the installation
