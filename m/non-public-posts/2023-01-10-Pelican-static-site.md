---
layout: post
title:  "Pelican static site genator"
date:   2023-01-10 12:00:00 +0000
categories: Code
---
# Using Pelican to create static websites 

Developing and maintaining a traditional static website project with only HTML, CSS and JS is hard when you reach a certain amount of content.

Static Site Generators (SSG), such as Pelican, enables the use of a templates to define the structure, layout and generate the internal navigation of your site. Then they export the full site into pure static site consisting of HTML, CSS and Javascript files.

## Steps
Created based on the *pelican-quickstart* template.

Initial setup after cloning repo
> git clone git@github.com:AttilaVural/pelican_static_site.git

> cd pelican_static_site

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

> git push -u origin

## Github pages compatibility
Set *RELATIVE_URLS = True* in pelicanconf.py, otherwise css will be not found when served from GitHub pages.

## Custom themes
By default, a new project created using the *pelican-quickstart* function, will use the pre-packaged theme stored in *\\env\Lib\site-packages\pelican\themes* (assuming you installed pelican in a virtual python environment).

In order to customize the layout and functionality of your site, the theme files need to be edited.

Custom themes can be installed by creating a "template" folder in your project root, downloading the custom theme into this folder and finally updating pelicanconf.py with *THEME = "templates\ \<name of the folder of the theme folder which you copied into the theme folder>"*.

## notes 2023.01.13 
if you add a code block in the top most of the page, the page loads the code block wrong and executes the html code instead of just showing it.

**You cannot add the mermaid plugin to pelican**

More specifially, pelican uses the python markdown package and mermaid is not on the list of supported extensions: https://python-markdown.github.io/extensions/
it is not even on the list of unsupported extensions: https://github.com/Python-Markdown/markdown/wiki/Third-Party-Extensions

otherwise it would simply have been a question of manually configuring the markdown extension by adding:

	MARKDOWN = {
		'extension_configs': {
			'markdown.extensions.codehilite': {'css_class': 'highlight'},
			'markdown.extensions.extra': {},
			'markdown.extensions.meta': {},
			'markdown.extensions.md_mermaid': {},
		},
		'output_format': 'html5',
	}

which is just the default included markdown extensions (see https://docs.getpelican.com/en/latest/settings.html) and the mermaid one included in the bottom. I interpolated this from this page for the python markdown package: https://pypi.org/project/md-mermaid/.

but somehow it doesn't work and the pelican compilar in CLI (command prompt) gives this error when recompiling: "No module named 'markdown.extensions.md_mermaid'". I just dont think it is supported by pelican.

## This is why I choose jekyll over pelican:

Jekyll is inbuilt into github pages, meaning I don't need to compile on my local pc and then push it to my github repo. I can simply clone a repo like (link to minima repo here) and GitHub Actions will automatically compile the static site. Editing posts and articles can be done directly through the github website UI.
