---
layout: post
title:      "It's not Friday the 13th but Json is here..."
date:       2018-08-30 19:48:17 +0000
permalink:  its_not_friday_the_13th_but_json_is_here
---


Working with Json has been far from horror-ible!  ok...  enough corniness - this is not the field of dreams...  

Although working with Json did make working with structured data a dream... (sorry)

The ability to stresslessly grab bits of data from an Json object as you need it is a huge benefit when trying to reduce the cost of transfering data in your app.  In simple terms you can say it is hash like - keys and values - but the overall structure makes it easier to deal with in my opinion.  When you look at the data you can actually see an object -  it doesn't just feel like a bag of data being thrown at you.

for example - an address book entry is how you would expect it to be:

{
     "firstName": "John",
     "lastName": "Smith",
     "address": {
         "streetAddress": "21 2nd Street",
         "city": "New York",
         "state": "NY",
         "postalCode": 10021
     },
     "phoneNumbers": [
         "212 555-1234",
         "646 555-4567"
     ]
 }
 
 much better than CSV:
 
 (John, Smith, 21, 2nd Street, New York, NY, 10021, 212 555-1234, 646 555-4567)
 
Just try and grab only the zip code from a CSV file...

Guess who wins...
yeah - This Guy \/
![](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRzjLYkJF6NNIuf-d-c_EhWULgVnwlrHkK_UWiBqB27bVXhUQ8vZQ)

JSON.parse.villain

villain.name = "Json"

It's not just me...
if you are using Json with C++ you can even use the Voorhees library: http://tgockel.github.io/json-voorhees/



