---
layout: post
title:      "Sinatra Project - Active Roster"
date:       2020-09-21 05:34:54 +0000
permalink:  sinatra_project_-_active_roster
---


After a few weeks of learning ORMS, SQL, Active Record, and Sinatra, the time has come to put all of that material together. 

Going into project week, I felt I had a pretty good grasp on the concepts and just needed to piece all that material together to build my project. Getting started with the Corneal gem was extremely helpful in building the file structure for MVC. I began by builing my database tables with all of the columns I thought I needed (more on this later), and then seeding those tables with some data to play with to allow for more effective testing. 

I built my belongs_to model, views and controller  first, and wanted to fufill the project CRUD requirements on this side of the project. Creating the associations to my has_many model, it seemed parts were falling into place, along with the signup and login processes, making sure I did not forget about the other details of the project, as in validations and not allowing other users to modify information that does not belong to that specific user. Playing with the helper methods really allowed certain pages to be secure. 

When I felt my MVC was built, with my login/logout and signup functions, I felt I could add little more. Going back to the Sinatra Complex Form Lab, I wanted to implement certains features of that lab into my project. This was the most challenging for me. After a variety of errrors, I nearly scraped the entire idea, but I kept on trying and was able to get it working the way I wanted it to. It was the last code I needed to write and it literally took hours to implement. The errors I experienced was: no implicit conversion of Symbol into Integer
After adding binding.pry in numerous lines of my teams_controller.rb, I saw all of params were successfully coming in, but trying almost every resource I possibly find, it still would not work. I went through my terminal and found the following error:

ActiveRecord::UnknownAttributeError: unknown attribute 'team_player_ids' for Team.
from /home/aleebrady/.rvm/gems/ruby-2.6.1/gems/activerecord-4.2.11.3/lib/active_record/attribute_assignment.rb:59:in `rescue in _assign_attribute'
Caused by NoMethodError: undefined method `team_player_ids=' for #<Team:0x00007fffbde70af8>

Then I realized, I needed to add more columns to my database table for teams so it could store the team_player_ids. 

Running another db:migrate to add the missing tables, resolved my troublesome issue. 

I feel like that was the biggest take away from this project, as you build your MVC and the bigger it gets, things can get tangled up and you. Using all of your resources from the post, to params, prys, and even the messages in the terminal can be very informative to help find the root of the problem.

Overall, I feel happy with this project and definitely learn a lot in the last serval weeks. Now it's time for Rails, which is a whole different animal from how some people make it seem. 

