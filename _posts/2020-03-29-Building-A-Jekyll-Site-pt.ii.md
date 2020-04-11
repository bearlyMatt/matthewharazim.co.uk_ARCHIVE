---
layout: default
title: Building A Jekyll Site pt.ii
author: matthewharazim
categories: amateurCoder,tutorial,nerd
---

# Welcome
So you decided to keep soldiering on after you lost hours on the install alone. Good for you, I'm proud! Let's recap what we've accomplished so far: we have _capable hardware_, a _full ruby install_, and _Jekyll_. Now that you're cuppa has been made, we're going to continue and create a wonderful new Jekyll file structure and learn how we can deploy a local version of our shiny new site, and ponder about what it will look like when it's finished.

## Disclaimer pt.ii
Once again, almost all of this information is ~~Frankenstein-ed~~ Frankenstein's Monster-ed  from a plethora of online resources, most notably <a href="https://jekyllrb.com/docs/step-by-step/01-setup/">Jekyll's own step-by-step tutorial</a>, and **INSERT EXTRA REFERNCES HERE**

Now that Gem has initialised all the Jekyll goodness, we need to create our website's _root directory_, which in this tutorial we'll call '_myWebsite_'. Assuming your terminal is still open from pt.i, envoke `mkdir ~/myWebsite` and then enter the directory with a `cd myWebsite`. Guess what, it's time, let's tell Jekyll this directory is going to be a website. We're going to create our own Gemfile to specify to Jekyll all the gems we'll be using for this particular build. Create the file by envoking `bundle init` from you _website root directory_, so in this case it would be run whilst in the directory `/myWebsite`. Now we'll add Jekyll as a dependency by opening the file (I like nano, but you can use vim, emacs, notepad) (`nano [or other file editor] Gemfile`) and add `gem "jekyll"`, which will most likely be the first lines of the file. Lastly, run `bundle` to **actually install Jekyll**. Congrats, you've done it.

Now, to go on a tangent, I knew from the get go that this site would only need static content. No need for any form of dynamism, simply a basic blog module and some links for information about yours truly. I tried running Wordpress, creating my own basic HTML file structure, but my main issue was that all these tutorials required the usage of databases such as MySQL and MariaDB. Coming from the arts background, I have no idea how any of that works, and I love using hierarchical data structures to keep my mind in check by using tools such as emacs org-mode to create things. Jekyll works completely sans-databases. Simply create your own folder structure and Jekyll magically transforms it into a fully fledged website. Seriously, I think I'm in love.

Jekyll creates websites based on directory structure, and tags within the web pages/blog posts you create. Here's a brief look at the structure of matthewharazim.co.uk

Breaking this down, we can see that in the
* _Website Root_ directory there are all of the linkable pages I want, i.e. my About, Contact and Home(Index) page.
* _Layouts_ contains .html files which are full of delightful _Liquid_ tags (a great system employed by Jekyll to create global variables etc.), one for each 'type' of static content I require: so blog posts, pages, and a default.
* _Assets_ is more like a file server-esque folder where any images, documents, or media files I want to display or host on the website lives, therefore to display an image, the markdown would read:
<br>`![Directory Tree](~/hyde/_assets/exampleImage.jpg "Directory Tree")`
* _Posts_ is just what it sounds like; a diretory for blog _Posts_.
* _Public_ is a little different, some people use it instead of an _ _Asset_ directory. The reason I have it is due to the use of the <a href="https://github.com/poole/hyde">Hyde</a> theme, which holds all its .css files.

Let's start our website by creating our first page in the _web root_ directory: `nano hello.md`. Jekyll magically transforms markdown into html, so you can use either .md or .html file extensions.

The single most important part of any Jekyll document is the front matter, which must contain a section delineated by `---` at the beginning and the end. In this section we can get Jekyll to utilise specific layouts, such as those for pages or blog posts, apply metadata such as author, title, and any categories or tags for searching purposes. So if we added this to our `hello.md` page it would look something like<br>
`---
layout: page
author: matt
title: Hello
category: pages
tags: about, hello
---`
