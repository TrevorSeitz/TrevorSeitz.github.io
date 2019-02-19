---
layout: post
title:      "Sometimes the basics are the best!"
date:       2019-02-19 21:44:10 +0000
permalink:  sometimes_the_basics_are_the_best
---


I have been trying for days to figure out how to roll through a list of photos and save them...

I started with .map - that great little helper that gives you a whole new array after modifying the elements of the original array.  It didn't really work...  actions were happening all over the place when ever they wanted to and ended up creating a bunch of undefined objects.  

So, it was time to try some async actions - miricles if you ask me!!!  But, that only helped a bit.  each function would work async but the bigger action the loop would just plow through...  I tried many different versions putting asyncs and awaits in various places but there was always a problem.

I broke the various steps out into small steps and tried async await on each one.  It still wasn't quite right - elements would get out of order - there is an if/else statement and it would async on either leg but not on the statement as a whole.  The outputs would still get mixed up and out of order...

forEach had the same problems...

I finally got back to the good old for loop: for (let i = 0; i < allLocalPhotos.length; i++) 

With all the advantages of the newer loop methods, it was up to the first onw I learned to save me!!

The for loop allows things to be done in order, clunky order...
