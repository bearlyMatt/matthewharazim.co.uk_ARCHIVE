---
layout: default
title: Building a Jekyll Site pt.i
author: matt
categories: [amateurCoder, tutorial, nerd]
tags: [raspi, raspberrypi, coding, website, hosting, programming]
---
# lets begin
So to start off, I want to make it very clear: I've had a lot of free time with the delightful social distancing from the Coronavirus (COVID-19) and decided to mess around with WSL, Raspberry Pi and the internet. I still have little to no real idea how to delve deep into the configurations for Jekyll, Apache and Raspi... **yet**. My biggest trouble was actually hosting Jekyll on my Apache server, but I'm getting ahead of myself (more on that later).

## disclaimer
A lot of this information is regurgitated and repurposed from the already easy-to-follow <a href="https://jekyllrb.com/docs/">Jekyll Quickstart Guide</a>, and really it's worth a read in of itself. The step-by-step tutorial is actually fantastic to learn how the basic structures of Jekyll work, as well as how .yml files should be formatted (this will definitely help debugging later on!).

## what you'll need
<br>
* some form of hardware (it could be a Raspi like me (I used the A+ with WIFI), the old PC I know you have in a corner unused and unloved, or just your laptop because you thought you'd give it a go and have no real issue with learning the skills to file away for later use).
* a server platform of some sort (NGINX, or Apache seem to be the favourites)
* a desire to host some form of _static_ website
* ruby
* jekyll
<br>
So, lets assume you already have hardware ready to go, if not and you're using a Raspi (any model), the single greatest resource I have found for frankensteining a server out of it can be found at <a href="https://habilisbest.com/category/Raspberry Pi">Habilis Best</a> and follow the secure personal server tutorials. Even if you have no desire to deploy your server to the internet, HB shows lots of tips and tricks to make sure you're the only person who can authorise any form of elevated functions. The man is a hero. After all your `sudo apt-get update` and `sudo apt-get upgrade`'s that you might be performing (of course I'm using debian as my server distro) I tend to start with a clean install of ruby. I envoke `sudo apt-get install ruby-full build-essential` and the wait for the full installation.

Once Ruby has installed, you can check the other pre-requisites *GCC* and *Make*, which you can run `gcc -v`/`g++ -v` and `make -v` to see what version you are running (or to check whether you have it installed). If anything comes up as being unrecognised, or not installed, a simple run of `sudo apt-get install [gcc]/[make]/[any other package] -y` will automatically download and install the latest version.

Right, you've got Ruby, you've got the other packages, it's time to install Jekyll right? *Wrong*. The next part will allow you as the logged in user to run Ruby Gems (little self-contained programs) as opposed to only the root (or super) user. 
```
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```
Now we can finally install Jekyll by running `gem install jekyll bundler`. I've found that this part takes the longest time. Go grab a cuppa and we'll continue soon...
<br>
<hr>
