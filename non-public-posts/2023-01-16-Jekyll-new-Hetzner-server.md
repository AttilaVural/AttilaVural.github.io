---
layout: post
title:  "Creating jekyll site using the Ruby CLI"
date:   2023-01-16 13:00:00 +0000
categories: Code
---
Note: I prefer the method of just copying the minima repo (link here: ...). Note that when you generate the site using the below method with the Ruby CLI, you also get a jekyll site with the minima theme as per default, but for some reason many folders and files are not including, and you have to create them yourself in order to customize the site (I wanted to add mermaid chart compability). However, the build process constantly crashed, when I tried creating these files and folders. I think the CLI generated jekyll sites are for hosting outside github pages - either locally or on another webserver, which does not have inbuilt jekyll support like github pages.
  
**Do not go with IPv6 - you need IPv4**

Reason: Putty cannot ssh to an IPv6 server. It simply does not support IPv6 connection. I tried using square brackets and tried using both port 22 and 222, but nothing worked. From then on, I could only use the terminal built into the Hetzner web-interface, which was terrible, as all the keys were mapped differently, than what I am used to. Also, the resolution was bad.

Filezilla is said to have inbuilt IPv6 support, but this can only be used for managing files. I could not get that to work though, and the Hetzner documention only mentions FTP/FTPS support for their "Storage Box" products.

**Normal workflow when connecting to a new server for the first time:**

```mermaid
  graph TD;
      1[Create your public key and private key using putty]
      1--->2[Give public key to server host]
      2--->3["Convert your private key to putty file (.pkk) format using puttygen"]
      3--->4["Load the .ppk file into putty (Category > Connection > SSH > Auth)"]
      4--->5["Connect using the IPv4 address on port 22"]
```
Now in order to update the list of ubuntu packages that you can install:

> sudo apt-get update

**Installing Jekyll**

> sudo apt-get install ruby-full build-essential zlib1g-dev

From the Jekyll website:

*Avoid installing RubyGems packages (called gems) as the root user. Instead, set up a gem installation directory for your user account. The following commands will add environment variables to your ~/.bashrc file to configure the gem installation path:*

> echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc

> echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc

> echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc

> source ~/.bashrc

Now install Jekyll: 

> gem install jekyll bundler

Create a Jekyll site:

> jekyll new my-awesome-site

> cd my-awesome-site

Add "#" to the beginning of the line that starts with gem "jekyll" to comment out this line.

Add the github-pages gem by editing the line starting with # gem "github-pages". Change this line to:
> gem "github-pages", "~> GITHUB-PAGES-VERSION", group: :jekyll_plugins

Replace *GITHUB-PAGES-VERSION* with the latest supported version of the github-pages gem. You can find this version here: ["Dependency versions."](https://pages.github.com/versions/)

From the command line, run: 
> bundle install.

To test the site, type the following, where "--host=\<server public IP adress\>" is needed, because otherwise the jekyll site will only be accessible through "localhost", which is not an option, if you are accessing the server remotely:
> bundle exec jekyll serve --host=5.75.230.166

Now to export it to you local PC, open a local CMD session and type:
> scp -r root@5.75.230.166:/root/my-awesome-site -r "C:\Users\ATVQ\OneDrive - Novo Nordisk\Desktop"

Now open the \_conf.yaml file and make sure these two lines are like so:
> baseurl: "" # the subpath of your site, e.g. /blog

> url: "https://attilavural.github.io" # the base hostname & protocol for your site, e.g. http://example.com

Now upload the jekyll site source files the *topmost* directory of you github pages repo and view it in the browser at https://attilavural.github.io. 

The folder structure should be like this:
```
<username>.github.io/
├─ _posts/
├─ .gitignore
├─ 404.html
├─ Gemfile
├─ Gemfile.lock
├─ _config.yml
├─ about.markdown
├─ index.markdown
```
