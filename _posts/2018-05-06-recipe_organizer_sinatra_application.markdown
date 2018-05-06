---
layout: post
title:      "Recipe Organizer Sinatra Application"
date:       2018-05-06 19:15:43 +0000
permalink:  recipe_organizer_sinatra_application
---

Recipe Organizer is a sinatra web application that uses the Model-View-Controller architecture. The user can create an account and when logged in can input their favorite recipes so they can reference them at a later time. To facilitate organization and easy access to stored recipes, the user assigns each recipe a category (e.g. Brunch). When accessed later the user can choose to view his or her recipes either by category, or all at once in alphabetical order by name. 

Recipe Organizer is a CRUD application, allowing users to create, view, update, and delete their recipes. The app does not allow a user to update or delete another user's recipes. Additional functionality that could be implemented in the future is to allow a user to see other users' recipes and to allow users to share recipes and send messages to each other. 

The app validates user input and utilizes rack-flash to generate error messages. 

![](https://i.imgur.com/fPJjyUx.png?1)	

*A user's recipe categories. User can then select a category to view that category's recipes.*


![](https://i.imgur.com/UxK9lK8.png?)

*A user's full list of recipes.*


![](https://i.imgur.com/hs3CB1e.png)

*A user's recipe for a Manhattan cocktail.*


![](https://i.imgur.com/1zjlQGF.png?1)

*Error message after attempting to sign up. User accounts must have a unique username and email address.*



	
