---
layout: post
title:      "One little mistake caused a nightmare through poor trouble shooting... "
date:       2018-09-22 16:06:47 +0000
permalink:  one_little_mistake_caused_a_nightmare_through_poor_trouble_shooting
---


I was setting up Strong Parameters in my Rails backend and couldn't remember the exact format for the statement, so I googled...

the format I found was: 
      params.require(:user).permit(:id, :account_id, :name, :title, :info)
			
To which I thought "Ding!" got it!

Then in my Places controller I wrote:
      params.require(:name).permit( :venue, :longitude, :latitude) - because of course I wanted to require the "name" parameter...  that is where my trouble began.
			
I had forgotten the details of the how and the WHY!

Then, during the trouble shooting I did two thing that caused me more pain:   I moved the whole strong param statement to my model (and then didn't move it back after realizing that the move didn't cure the problem) PLUS I turned off wrap_parameters.rb in my initializers (and then didn't change it back after realizing that not wrapping the parameters didn't cure the problem) because I noticed that I was getting two sets of parameters when I called params in pry.   

After a few hours of googling and doing more wrong things I put out the Bat Signal to my cohort with a brief description of what was wrong and what I had tried. Alyssa came to my rescue!  after some back and forth and a few trial and errors she had the idea to ditch the "required" part and just use the permit...  

IT WORKED!!

I did a few tests and it still worked!!

I sent my thank yous and went off coding...

Then, because the Technical Coaches at Flat Iron are so awesome... I received a message with a little more info on the problem.  Jenn saw my question, read the conversation and explained that the data should be wrapped by the model name and because my data wasn't that is why required didn't work and getting rid of it did.

Now, if you remember, I turned off wrap_parameters.rb...  well, not so much "turned off" but changed:   wrap_parameters format: [:json] to wrap_parameters format: [].   That had removed the set of parameters that started "{'place' => {...".  Luckily I REMEBERED... 

I reset the wrap parameters and added the require(:place) - using the name of the model not the parameter - and everything worked properly!!  

I hope this little tale has taught you at least one thing:  When troubleshooting, ALWAYS RESET what you changed if it doesn't affect issue.

The wrap parameters set to [] had caused an error when I tried using the model name during troubleshooting because  "{'place' => {..." wasn't there...  The 

The second this: LEARN, don't just remember...  when you learn you get the how, and the why...  If I had learned that you REQUIRE the MODEL to only PERMIT certain PARAMETERS, when I looked up the format for strong parameters, I would never have had the problem.

The third thing I hope you take away is:  use your resources!  It doens't matter how isolated you feel, we have gained a huge network just by being part of Flat Iron School!!  Alyssa and I had been in Study Groups together, but we didn't do any projects together and are in different parts of the world...  But we have the resource of slack and the connection of Flat Iron.  It was great that she was able to help me so quickly but I also had the ability to reach out on the react channel, Vals-coachin-crew, or the online-web-developer channel - and that is just within Flat Iron, there are a number of other resources out there and as we meet people through work or meetups our hive mind grows!

the fourth thing I hope you take away is:  when using Strong Parameters, you REQUIRE the MODEL to only PERMIT certain PARAMETERS...

Oh, and a fifth thing... you do validations in your model... "validates :name, ... "


Happy coding!!



Thanks to Both Alyssa and Jenn for all their help!!
