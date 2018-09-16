---
layout: post
title:      "Community Space"
date:       2018-09-16 00:06:52 +0000
permalink:  community_space
---


My final project in Flatiron School is Community Space, an online discussion app where users can start discussions on any topic they'd like and share their opinions on the discussion topics by submitting comments. The idea is to create an atmosphere where users can freely express their ideas in a respectful manner, creating a vibrant dialogue. The app utilizes React for the frontend, with Redux to manage state, and a Rails API backend, connected to a SQLite3 database. 

The app was easy to setup thanks to `create-react-app` and the rails new api generator, which provided the overall folder structure as well as basic dependencies. On the frontend, the app is composed of four routes, plus one route for each discussion where users can view that discussion's comments and add comments. Currently, users can browse the list of discussions, view the list of comments for each discussion, create new discussions and comments, and delete comments.  In the Rails API, there are two models: comment and discussion: a discussion `has_many` comments and a comment `belongs_to` a discussion. 

I would say the most difficult part of the project was executing the AJAX requests correctly (GET, POST, and DELETE requests were used), making sure the correct data was returned, and making sure the data was then appropriately dispatched.

I felt this project was a great way to revisit the major content of the course. By creating a Rails API, I was able to refresh my memory on model associations, strong parameters, RESTful routes, serializers, and other major Rails concepts. I found building both the frontend and backend components at the same time to be very rewarding and look forward to implementing improvements to the app in the future.
