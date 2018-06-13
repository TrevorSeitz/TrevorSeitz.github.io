---
layout: post
title:      "Using "before do" in a controller"
date:       2018-06-13 17:41:51 +0000
permalink:  using_before_do_in_a_controller
---


I am working on my Sinatra app and after about the 15th time (possible exaggeration) of typing “@user = User.find_by_id(session[:user_id])” I was getting pretty fast at typing it…  and pretty bored with it too…  Luckily, while googling for solutions to a problem I discovered someone who was using “before do” in her controllers and a lightbulb went off in my head! 

I put my @user statement into a 'before do' and commented it out everywhere else in my order_controller - BINGO, it worked.

I looked around and found a few more statements I had been using multiple times in multiple controls.

Now my controllers include a custom version of the following code:

  before do
    #Check if User exists
    if !!@user = User.find_by(email: params[:email])
      redirect "/users/new"
    end
    #Check if User is Logged in
    if !is_logged_in?
     #if the user is not logged in - go to login page
      redirect "/login"
    end
    #Create @user
    @user = User.find_by_id(session[:user_id])
    #Create @store
    @store = Store.find_by_id(@user.store_id)
  end

This loads as soon as the controller is called, each time the controller is called!  

I may be naive and this may be the absolute worst way to do it, so use this with that caution in mind, but it does shorten the controller and many of the controls inside.   

