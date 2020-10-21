---
layout: post
title:      "Off and On the Rails "
date:       2020-10-21 21:01:11 +0000
permalink:  off_and_on_the_rails
---


Coming off my Sinatra project, I felt I had a lot of momentum and was feeling comfortable going into the Rails module. The first week was not bad, but as I proceeded through the lessons, you realize how robust Rails is. You understand there are so many moving parts to consider. Building your models, controllers, and views are similar to Sinatra, but implementing all the helpers, partials, and methods built into the Rails framework can be very confusing at first. Although the more repetition you have working with the framework, the more familiar and comfortable you will become. 

Unlike Sinatra, going into the Rails project, I did not have a specific idea of a domain I wanted to use. Everytime I thought I had a good idea, I realized it did not (or so I thought) meet the many-to-many requirement. I always came up with a one-to-many relationship, or convince myself it was. So I thought of a simple relationship I am familiar with, is a Client-Trainer relationship and the workouts that join them together. 

I started my project running a resource generator  for the User model, and creating a session_controller, to build the signup, login, and logut actions.  After building the routes, it tested successfully, and  the session would redirect_to the user_path(@user) page after logging in.  

I countinued to use the resource generator for the other models, and I also used the rails g migration to add some columns to the tables that were needed to create the relationships between models, as in the foreign_keys in the workouts table. As I built the models and added the macros to open up the relationships, the project was coming together. 

Going through the list of requirements, I was really focused on making sure I had the nested routes and scope methods completed. My approach was to keep these as simple as possible. Looking up a simple seach bar in the Rails documentation really helped completing the scope method requirement, as I just had it seach by workout_type. The nested routes, was pretty straight forward using the labs as a reference. 

My biggest challenge was the omniauth portion of the project. I once again followed the lab, but I forgot to create the omniauth.rb file in  /config/initializers. I totally skipped over that part of the process, and had me scratching my head for a little bit. Once I realized my mistake, it logged into facebook successfully. Although, when testing it the day after, the server would hang up at the callback phase, but still login to facebook, and not redirect back to the user_path. I did not change the callback route: 

get '/auth/facebook/callback' => 'sessions#fbcreate'

After researching, I rebooted my machine and oauth successfully worked again. 

I looked for places to DRY up my code, as for forms, creating before actions and setting params for specific models. 

One thing I did not do in Sinatra, was add a little of styling. I looked at some bootstrap tutorials and followed along and slightly changed the font style, and added an image using image_tag. I still need to find better resources for this, but I'm glad I tried something different and definitely want to build this skill along with the concepts learned in Rails so far. 

In conclusion. This was a very difficult project compared to Sinatra. Focusing on the requirments really helped give me direction in completing the tasks expected to be displayed. I know there's a lot more to learn, but this being my first Rails project, I feel in learned a lot and now have a good foundation of the process in making a Rails app. 




