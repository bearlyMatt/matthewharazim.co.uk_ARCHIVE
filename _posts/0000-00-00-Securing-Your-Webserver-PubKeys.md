---
layout: posts
title: Securing Your Webserver with PubKeys
author: matt
---
# PubKey SSH Authentication

One of the confusing things I've always found regarding SSH and security is the difference between password authentication and PubKey authentication.

Over the past year, I decided to invest in a password manager - Remembear to be exact - as a means of increasing my online security regemen. After being constantly hacked through Facebook, my BT email account, and various other online aliasesm, I felt like taking the next step and going full on character string passwords with no means of easy ~~remembering~~ remem**bear**ing. Of course, this is all well and good, but with the way force-brute attacks can work this day and age, purely a password is not the highest form of defence: hence the slow but inevitable ~~betrayal~~ rise of 2FA, or Two-Factor Authentication[^b5831a34]. Think of your SSH PubKey as the Grandfather of 2FA, who has survived the Great War, having been on the frontlines the whole time, with nary a scratch.

[^b5831a34]: Did you get my delightful _Firefly_ reference?

For our Pi (or general Linux) server, getting an SSH key is actually quite simple - I was merely being thick. 
