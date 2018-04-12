---
layout: post
title:      "How I learned to find the CSS tags and conquer the CLI"
date:       2018-04-12 18:02:01 +0000
permalink:  how_i_learned_to_find_the_css_tags_and_conquer_the_cli
---


The Ruby CLI project was a fun challenge and a great was to close out the section.

I chose to scrape mufon.com - the website for the Mutual UFO Network, a nonprofit group that investigates UFO sightings in a scientific manner.  I chose this site mainly because I was confident that no one had done it before.

The website has many different sections and I chose to scrape the UFO news section, the MUFON news section and the table of the most recent reported sightings.  I did this because it offered me the opportunity to scrape two different pages with the same structure and build 2 different lists to choose the next level from and it offered the chance to scrape a table.  I only have one level of scraping on the table because it was, in my mind, bonus info.

The first look at the structure of the UFO news page had me thinking it would be easy to figure all the tags out.
![https://drive.google.com/open?id=1C77CG1LUepPmu6IOhz6LYIZkvAyaTDmi](https://drive.google.com/open?id=1C77CG1LUepPmu6IOhz6LYIZkvAyaTDmi://)

But I was in for a surprise... What seemed like an easy read would often not give me the information promised.  
![https://drive.google.com/open?id=1C77CG1LUepPmu6IOhz6LYIZkvAyaTDmi](https://drive.google.com/open?id=1C77CG1LUepPmu6IOhz6LYIZkvAyaTDmi)

The well formated tags held surprises that forced me to "gsub" out things t get at just the information I wanted. things like a calendar icon hidden before the date of the post that you can't see until it is parsed and becomes a series of n\t\ symbols.

When I found the magic combination of tags and gsubs, the parsed elements became part of the objects I was creating and formed the list I had imagined.  It suddenly seemed so easy...  It seemed even easier when I parsed the MUFON news and it fit as well!!  

Then the table came...  

I realized that the toughest part of creating a scraper is figuring out how the information you want to present is represented in the CSS tags...  it is going to depend on the author of the website more than you own skills.  If you and the webpage author use and folllow the same "best practices" you may find it all very easy but if there are no standard practices let alone BEST practices you will be in for a challenge.

In the end, the toughest parts for me were actually made tough by me...  I overwhelmed myself because I have never made a gem...  I have never started from scratch...  I had never used the bundler...  well, now I have - and although I'm not 100% on the gem creation none of it was as bad as I made it out to be.

and so here it is:
![https://drive.google.com/open?id=1dxsFgGKVFIjbSrVNusHV8pIDZvv_sXrI](https://drive.google.com/open?id=1dxsFgGKVFIjbSrVNusHV8pIDZvv_sXrI)
![https://drive.google.com/open?id=11cVAHTJn7jcWuACBiuwrD3QIgTuYihL1](https://drive.google.com/open?id=11cVAHTJn7jcWuACBiuwrD3QIgTuYihL1)
![https://drive.google.com/open?id=124bBKMXotF9vNu4hZcMPWeq7_XAvRqMn](https://drive.google.com/open?id=124bBKMXotF9vNu4hZcMPWeq7_XAvRqMn)

