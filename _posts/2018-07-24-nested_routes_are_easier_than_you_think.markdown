---
layout: post
title:      "Nested Routes are easier than you think!"
date:       2018-07-24 21:56:20 +0000
permalink:  nested_routes_are_easier_than_you_think
---


![](https://drive.google.com/file/d/1ckRaW8UD40gtcEdWuKckWHrYqevE1AvH/view?usp=sharing)

When you first look at that long list streaming down the page after you typed "rake routes" the first thought may be "What have I done?

But don't worry, it's not the big deal it seems - it's a very helpful bit of info and it can be managed!

In the routes.rb file you have to set your nested routes to get the most of routes:

![](https://drive.google.com/file/d/1wx_pWBI-ghgLVZaSIW3DO693JGD7KIR5/view?usp=sharing)

This is what allows you to have that nice fancy URL: /users/1/dog/5 when you are looking at a show page.

It also help you get your head around all that happens in the controller - its all there on the right.
![](https://drive.google.com/file/d/1VWi0I7-VP2BSZusCLu5Az5JwhaEVda3B/view?usp=sharing)

There are only a few actions for the controller but there are many ways to get there if you are nested...

if you want to add a new dog to your list -  you are gonna do that with the new action in the dogs controller ( or dogs#new as it is desplayed on the list).  You have a choice of urls to use :  /dogs/new, /users/:user_id/dogs/new each with their own path.  /dogs/new has new_dog_path while /users/:user_id/dogs/new has new_user_dog_path - it only matters how you want to show the user where they are...

Once you get used to the layout, you'll find yourself skimmimg through the lines looking at your favorite column to find the path or the action you want.

you don't need a map to figure out your route - these routes are the map for your app!

