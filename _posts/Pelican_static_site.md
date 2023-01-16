# Using Pelican to create static websites 

If your site has a minimal amount of styling and HTML boiler-code (navigation bars, footer links etc.), then developing and maintaining a traditional static website project with HTML, CSS and JS files would be a lot of work.

Static Site Generators (SSG), such as Pelican, enables the use of a templates to define the structure, layout and internal navigation of your site, so you only have to write the blog posts/articles. Then they export the full site into pure HTML/CSS files.

Pelican does not make much use of JS unlike other SSG's like nuxt.js or hugo.

## Steps
Created based on the *pelican-quickstart* template.

Initial setup after cloning repo
> git clone -b test git@github.com:AttilaVural/AttilaVural.github.io.git

> cd AttilaVural.github.io

> python -m venv env

> .\env\scripts\activate

> pip install -r requirements.txt

Compile site
> pelican content

Show site in browser: run pelican listen with regeneration (-lr)
> pelican -lr 

Push changes
> git add .

> git commit -m "edited x and y"

> git push -u origin test

## Misc. changes
Set *RELATIVE_URLS = True* in pelicanconf.py, otherwise css will be not found when served from GitHub pages.

## Custom themes
By default, a new project created using the *pelican-quickstart* function, will use the pre-packaged theme stored in *\\env\Lib\site-packages\pelican\themes* (assuming you installed pelican in a virtual python environment).

In order to customize the layout and functionality of your site, the theme files need to be edited.

Custom themes can be installed by creating a "template" folder in your project root, downloading the custom theme into this folder and finally updating pelicanconf.py with *THEME = "templates\ \<name of the folder of the theme folder which you copied into the theme folder>"*.
