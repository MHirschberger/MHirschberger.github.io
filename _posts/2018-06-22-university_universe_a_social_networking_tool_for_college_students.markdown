---
layout: post
title:      "University Universe: A Social Networking Tool for College Students"
date:       2018-06-22 21:12:40 +0000
permalink:  university_universe_a_social_networking_tool_for_college_students
---


University Universe aims to connect college students in their classes. A user can select a university, a course at the university, and view the posts that have been written for that particular course. Each post is categorized as a 1. current student post, 2. a course rating/review, 3. or other. The university and course index pages have a search bar to make it easier for users to find their desired items. 

University Universe is a Rails CRUD app that follows the Model-View-Controller architecture; users can create, read, update, and delete courses, as course information changes from semester to semester. Users can also update and delete their own posts, but cannot modify other users' posts. Universities cannot be deleted. 

The app features onmiauth; users may create an account or log in with Facebook if they currently have a Facebook account. The app validates new user data, ensuring their name and email address is unique. Validations are used throughout the other models to ensure data saved to the database meet the required criteria. Upon logging in, users can view their posts for all their courses and universities. 

![](https://i.imgur.com/cA8TPK8.png)
*University Universe homepage.*

![](https://i.imgur.com/6bYEjI0.png)
*Page showing the posts for a course.*
