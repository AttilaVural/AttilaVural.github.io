# Initial setup

Create a keygen. Choose eg. "C:/users/ATVQ/.shh"
> ssh-keygen -t ed25519 -C "att.vural@gmail.com"

Now go into GitHub web interface and paste the content of the "id_ed25519.pub" file into the textbox.

# Clone blank repo
Clone the repo using ssh (.git address)
> git clone git@github.com:AttilaVural:<repo name>.git
you can also clone using the https address of the repo, but do not do this - it forces you to login each time you want to push

Add changes and push (Python example)
> cd <cloned repo directory>
> python -m venv env
> .\env\scripts\activate
> pip install <your desired libraries>
> pip freeze > requirements.txt

Create .gitignore file
> type nul > .gitignore
> (echo env/) > .gitignore

Stage newly created/deleted/edited files
> git add .
Commit
> git commit -m "first commit"'

This is part is executed exactly now, since git will not create a master branch until you commit something)

Create <branch>
> git branch <branch>
Switch to <branch>
> git checkout <branch>

push contents of <branch> to origin (github)
> git push -u origin <branch>

Skifte til eksiterende branch med indhold og updatere filerne lokalt til branchens indhold
> Git checkout <branch >
> Git reset --hard origin/<branch>
