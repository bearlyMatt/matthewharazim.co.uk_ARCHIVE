---
layout: default
title: Building A Jekyll Site pt.ii
author: matthewharazim
categories: amateurCoder,tutorial,nerd
---

# Welcome
So you decided to keep soldiering on after you lost hours on the install alone. Good for you, I'm proud! Let's recap what we've accomplished so far: we have _capable hardware_, a _full ruby install_, and _Jekyll_. Now that you're cuppa has been made, we're going to continue and create a wonderful new Jekyll file structure and learn how we can deploy a local version of our shiny new site, and ponder about what it will look like when it's finished.

## Disclaimer pt.ii
Once again, almost all of this information is ~~Frankensteined~~ Frankenstein's Monster-ed  from a plethora of online resources, most notably <a href="https://jekyllrb.com/docs/step-by-step/01-setup/">Jekyll's own step-by-step tutorial</a>, and **INSERT EXTRA REFERNCES HERE**

Now that Gem has initialised all the Jekyll goodness, we need to create our website's _root directory_, which in this tutorial we'll call '_myWebsite_'. Assuming your terminal is still open from pt.i, envoke `mkdir ~/myWebsite` and then enter the directory with a `cd myWebsite`. Guess what, it's time, let's tell Jekyll this directory is going to be a website. We're going to create our own Gemfile to specify to Jekyll all the gems we'll be using for this particular build. Create the file by envoking `bundle init` from you _website root directory_, so in this case it would be run whilst in the directory `/myWebsite`. Now we'll add Jekyll as a dependency by opening the file (I like nano, but you can use vim, emacs, notepad) (`nano [or other file editor] Gemfile`) and add `gem "jekyll"`, which will most likely be the first lines of the file. Lastly, run `bundle` to **actually install Jekyll**. Congrats, you've done it.

Now, to go on a tangent, I knew from the get go that this site would only need static content. No need for any form of dynamism, simply a basic blog module and some links for information about yours truly. I tried running Wordpress, creating my own basic HTML file structure, but my main issue was that all these tutorials required the usage of databases such as MySQL and MariaDB. Coming from the arts background, I have no idea how any of that works, and I love using hierarchical data structures to keep my mind in check by using tools such as emacs org-mode to create things. Jekyll works completely sans-databases. Simply create your own folder structure and Jekyll magically transforms it into a fully fledged website. Seriously, I think I'm in love.
