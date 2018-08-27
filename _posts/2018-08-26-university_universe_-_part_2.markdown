---
layout: post
title:      "University Universe - Part 2"
date:       2018-08-27 00:46:30 +0000
permalink:  university_universe_-_part_2
---


This project is an extension of the Rails app University Universe, explained in my June 22, 2018 blog post. Four jQuery events were implemented with Ajax requests to enhance the user experience of the app. Three of these events are GET requests:  

1. On the University Index page showing the list of universities, the user can click a university's "View Courses" button to view the Course Index for that particular university side-by-side the University Index. 

2. When a user clicks on the "See Post Details" button for a particular post, it redirects to the post's show page. The user can then sift through the posts of that particular course with the "Next Post" and "Previous Post" buttons. 

3. On the user home page, there is a link "Click to View Your Posts" that display all of the posts that the user posted. This link can be toggled to display or hide the posts.

For Ajax GET requests, Active Model Serializer was used to serialize Rails data into a JSON format. The returned data was then manipulated and appended the DOM to display the newly formatted data to the user without a page refresh.

The fourth event included an Ajax POST request: on a course's post index page, there is a new post form at the top. The user can create a new post, which will be immediately saved to the server and displayed at the top of the post index page's list of posts. To achieve this, the form gets submitted and data from the form is serialized and submitted to the server. Rails then saves the new post and returns data as JSON. The JSON then gets manipulated and appended to the DOM.


