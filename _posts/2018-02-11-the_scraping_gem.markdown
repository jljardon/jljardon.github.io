---
layout: post
title:      "The scraping gem"
date:       2018-02-12 03:11:45 +0000
permalink:  the_scraping_gem
---

One of the things that we as developers have to face from time to time, not only as part of our profession but as a learning technique and practice, is to create something from scratch. In that endeavor, sometimes, we don’t always know where to start. So, for this purpose, I’ll take advantage that I just just finished my CLI Data Gem Project, and in this post, I would like to share a few things I’ve learned along the way with a brief explanation of the process and approach I took to complete it from start to finish.


## First things first
While I was reviewing the requirements and a few videos with helpful tips, I came to the conclusion that the first thing that should work on was the structure of directories were I will be putting my code. 

I used bundler since it not only helps you organize with a standard directory structure but it helps you with the creation of a few files that will come in handy.

![](https://imgur.com/IT6HFG8.jpg)

The command above creates a directory with the structure needed for a standard ruby gem project. As you can see it also helps with keeping your files organized and with some other files that I needed for the project(README.md, LICENSE, etc).

![](https://imgur.com/Xn7UVlQ.jpg)

**Note**: *As you might have guessed I didn’t name my project “example” I just wanted to illustrate how bundler creates a clean project directory and the files it generates.*

Once I was done with the project structure the first thing I did was to initialize a git repository and the make the first commit. This helped me have base to start building and from that point on I would have something to return to in case I made a mistake that I could not correct. This would also help me work with some one else if that were the case.

To initialize a git repository:

![](https://imgur.com/Uhhqrjz.jpg)

Bundler initializes the git repository but still I was required to make the first commit to create the master branch.

It is also recommended to include a .gitignore file, this will help you keep you github repository free of anything but your code(.gem files, test results and so on should be in this file). In my case I kept my personal notes of development in the same directory of the project but never publish them to the github repository.

![](https://imgur.com/BueL1Te.jpg)

After having the first steps of a project completed, my recommendation would be to look for the dependencies that it may need. In this case I added nokogiri, pry and colorize to my gemspec file. I used this step to fill in formation that is required for the gem:

![](https://imgur.com/yi5RQgj.jpg)


## The actual project 
For the gem I had the idea to start from the CLI and then create the models and finally the scraper. This would help me keep fixing the errors that the user may encounter from start to finish. 

The steps I took was to make sure that the gem worked as it was and that I had a configuration file that would let me keep al the required files organized. Bundler created this file for you with the name give to the gem under the lib directory:

![](https://imgur.com/AaMqsan.jpg)

As you can see I added al my dependencies here and the actual files where my classes where. This helped me simplify the declaration of dependencies in other places in this case the file that starts the application:

![](https://imgur.com/lDZbbDh.jpg)

A few helpful tips:
-	Make the code work first then refactor the optimize.
-	Commit frequently
-	Work on one problem at a time
-	Keep files and methods simple and organized
-	Remember [DRY and KISS](https://softwareengineering.stackexchange.com/questions/73065/what-are-dry-kiss-solid-etc-classified-as)

The functionality of the project would take probably too much time to explain, but in general what I did was:

-	Have placeholders of the objects I would later use
-	Add functionality and remove placeholders
-	Program only what is required
-	Test the results
-	Correct errors if needed
-	Commit successful functionality
-	Repeat until completion

The end result can be seen in the following repository:
https://github.com/jljardon/upcoming_games

As a final step I published the gem to:
https://rubygems.org/gems/upcoming_games

This last step took me some time since most of the tutorials that I found online didn’t explain completely each of the elements that the .gemspec file requires to successfully build the gem. Most of them are self explanatory but others are not. However you can see that pretty much you need to fill in the paths of the gem and the executable file.

![](https://imgur.com/5NRkNep.jpg)

Lastly to build and publish the gem:

![](https://imgur.com/C3WH156.jpg)

Overall I’m satisfied with how the project turned out, but as always there is room for improvement. I hope if you read this you enjoyed it. If you see any issues or suggestions, please post them in github repository.



