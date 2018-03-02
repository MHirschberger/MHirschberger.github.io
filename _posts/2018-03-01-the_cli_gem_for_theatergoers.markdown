---
layout: post
title:      "The CLI Gem for Theatergoers"
date:       2018-03-02 01:19:32 +0000
permalink:  the_cli_gem_for_theatergoers
---


For my first project in Flatiron School, I created a CLI data gem that provides the user a list of all shows currently playing on Broadway. The user can then drill down into a particular show to obtain that show's theater, the address of the theater, and show's plot summary. 

Data was obtained from broadway.org, a site maintained by the Broadway League, Broadway's national trade association. The data from this site was scraped using the module Open-URI, which returns the HTML content of the particular URL, and Nokogiri, a Ruby gem which parses through the HTML and returns the item of interest, based on the use of CSS selectors. 

When the program begins, a numbered list of shows is automatically generated and the user can input the number of any show to obtain more details. The user can also type `list` to repeat the list of shows or `exit` to end the program. 

![](https://i.imgur.com/GFz2PGe.png)

The details that the gem provide for each show include the theater where the show is playing, the New York City address of the theater, and a plot summary. The screenshot below gives an example.

![](https://i.imgur.com/b6qoQ6K.png)

The program will repeat until `exit` is inputted. The program will generate an error message for any number out of range or for any other entry besides `list` or `exit`. The program will generate a farewell message upon exit.

![](https://i.imgur.com/x9WWuUQ.png)

The gem is on [RubyGems](https://rubygems.org/gems/theatre_cli_gem)

Code for the gem can be found on [GitHub](https://github.com/MHirschberger/theatre-cli-gem/)
