---
layout: post
title:  "GIT initialization"
date:   2016-01-15 15:00:00 +0000
categories: Code
---
# Initial setup
**Create a keygen. Choose eg. "C:/users/ATVQ/.shh"**

ssh-keygen -t ed25519 -C "att.vural@gmail.com"

Now go into GitHub web interface and paste the content of the "id_ed25519.pub" file into the textbox.









# Clone blank repo
Clone the repo using ssh (.git address). Note: you can also clone using the https address of the repo, but do not do this - it forces you to login each time you want to push.

> git clone git@github.com:AttilaVural:\<repo name\>.git

**Add changes and push (Python example)**
  
> cd \<cloned repo directory\>

> python -m venv env

> .\env\scripts\activate

> pip install \<your desired libraries\>

> pip freeze \> requirements.txt

Create .gitignore file
> type nul \> .gitignore

> (echo env/) > .gitignore

Stage newly created/deleted/edited files
> git add .

Commit
> git commit -m "first commit"'

this is part is executed exactly now, since git will not create a master branch until you commit something)

Create \<branch\>
> git branch \<branch\>

Switch to \<branch\>
> git checkout \<branch\>

push contents of \<branch\> to origin (github)
> git push -u origin \<branch\>

do some work here ...

Skifte til eksiterende branch med indhold og updatere filerne lokalt til branchens indhold
> Git checkout \<branch\>

> Git reset --hard origin/\<branch\>
  
  
  
  
  
  
  
  
  
  
  
# Clone repo with files
Clone the repo using ssh (.git address). Note: you can also clone using the https address of the repo, but do not do this - it forces you to login each time you want to push.
> git clone git@github.com:AttilaVural:\<repo name\>.git

> cd \<cloned repo directory\>

**Run the code (Python example)**
> python -m venv env
  
> .\env\scripts\activate
  
> pip install -r requirements.txt

**Creating and switching branch**
  
Create \<branch\>
> git branch \<branch\>

Switch to \<branch\>
> git checkout \<branch\>

Skifte til eksiterende branch med indhold og updatere filerne lokalt til branchens indhold
> Git reset --hard origin/\<branch\>

**Push files to repo after changing stuff**
  
Stage newly created/deleted/edited files
> git add .

Commit
> git commit -m "first commit"

Push contents of \<branch\> to origin (github)
> git push -u origin \<branch\>




# Misc notes from another deleted post:
Push contents of <branch> to origin (github)
> git push -u origin \<branch>
  
**If you are not allowed to push your local changes due to content being updated on the branch**
  
Be carefull as this will override your local changes if they conflict with the upstream changes.
> git pull origin \<branch>
