---
layout: post
title:      "JS Project - The Most Challenging Yet"
date:       2020-11-23 20:19:38 +0000
permalink:  js_project_-_the_most_challenging_yet
---


Coming out of break week and having successfully passed my Rails review I felt momentum was on my side. I had the motivation going into JS in waiting grap the most important concepts of this module. As the weeks went on and time came for project week, I was a bit anxious , since I saw some many different ways to build out projects. Someone mentioned JS is like the wild west, going through all of the things I researched and read and after doing this project, I truly believe that statement is true. 

When reading the requirements  for the project, it seemed pretty simple compared to the previous projects. When going through the lessons, lectures and study groups, the demonstrations were a bit different when building out the project. Mostly how the examples came out, was eveything was in one index.js file. Then the intro to classes to create those separation of concerns made more sense to me. 

As I started to build out my own project, I wanted to take it slow and make sure I did not miss a detail, and prevent falling into a confusing bug the deeper I got into the project. I began in building my directory and separating the front-end from the api(backend). Running rails new with the --api flag, building out the has_many and belongs_to models, and building out the controller actions was all familiar territory. When I got my api pages to load correctly, I started working on my JS(frontend) side. 

I did a lot of research on bootstrap( since I have not used it before), to give it some styling, and added those scripts to the index.html. To make sure my index.js file was recognized, I just did a basic console, which appeared in the console of my web browser. I began with creating a fetch request for my Home model(has_many), and have those records append to the DOM. As I started to build my methods, I felt things coming together, but at the same time feeling overwhelmed. I created a separate class for my fetch requests, which organized the code a bit more, and cleaned up my home class a bit. I did the same for bids(belongs_to), I fetch the data with the correct home_id, and attached that to the correct record on the DOM. 

I was using a bootstrap form in my html file, which was not displaying anymore, So I moved it into its own class container, and wanted to use that for most POST ajax call. I reused my bid POST fetch code for home, and built out a eventlistener for my submit button along with a prevent default function. Going through a lot of different failures and errors, I was able to get my POST home function to work and get it to append to the DOM successfully. 

After a few days of tireless work on this project, I was able to get all of the requirements specified. I feel this was the most challenging project yet, but I know there is so much more to learn and with enough repetition and practice, I will get better a JS. 
