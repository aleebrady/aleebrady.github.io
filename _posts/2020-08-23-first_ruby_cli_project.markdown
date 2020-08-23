---
layout: post
title:      "First Ruby (CLI) Project"
date:       2020-08-23 08:42:33 +0000
permalink:  first_ruby_cli_project
---


After three weeks of READMEs, lessons, and labs, project week has finally arrived. This will test the ability to utilize the knowledge conveyed and instructed through those lessons and labs. 

The reference material provided to give you direction, and layout a plan to make a CLI program was pretty clear. 

- Create a CLI 
- Your CLI application must provide access to data from a web page.
- The data provided must go at least one level deep. A "level" is where a user can make a choice and then get detailed  information about their choice.

With all these requirements in mind. I wanted to do something I was interested in, instead picking a random domain to work through. So I decided to make a workout application to get specific workout details, about a specific workout. 

I started by creating my file structure and making sure I had all the files require to run my program. I created my entry point in the ./bin/cf_wods file. Creating this instance would allow my program to run when called in the terminal. When creating my cli class, I started simple, making a call method to welcome the user with a greeting. As the methods started to build, I realized I need to get data to populate for the user to experience a nice flowing program, that was somewhat useful and informative. I guessed it was time to implement the scraper. This part - for me at least - was actually the most interesting. I decided to get information from two different sites. The way some of the information was contained on the second site was a better formatted to iterate through to and get it to displayed the way I felt it was most useful to the user. For the data that was scraped, I need to put that data somewhere. I created a class variable set to any empty array  to contain the workout names, and the workout details were sent to a instance variable called info also set to an empty array. 

 After I had my structure all setup, all the methods I wanted to use, and all of the data I needed to scrape, I encountered one error after another. Some things were misspelled, or named differently. When my terminal would return error after error, I would just go through the lines it said it has a problem with check what was the specific thing I missed. Once I worked through that, and my workout data appeared, I felt a sense of relief I don't think I experienced before. Although I had this weight lifted, I still needed to tweak some things to get this CLI to flow better. When the workout details returned, it would be for all of the workouts, and not a specific workout. Any user would not enjoy scrolling through all workout details when they selected a particular one. So, I went back to my scraper to set up another method, and adjusted my workout class to accommodate that data. 
 
 
 Finally, after a few days of working on this project, it finally came together. With the help of my instructors seeing things I missed after being stumped for hours, they really answered the questions I needed answered. For that, I'm very appreciative. I wish I used the study groups sooner to really solidify what I've learned so far. I know there's a lot more to go, but having that support system was extremely helpful in getting over some of those barriers. This project really tested me in multiple ways, and is forcing me to create newer and better habits to learn and reinforce the material being presented. 
