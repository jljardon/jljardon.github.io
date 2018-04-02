---
layout: post
title:      "Sinatra Project – A social network"
date:       2018-04-02 02:45:32 +0000
permalink:  sinatra_project_a_social_network
---


Something that many people tend to ask themselves when using a social network is the amount of time and effort required to create the basic flow of an application that has content managed by its users. So, to show what is required to develop an application like that I’ll use my Sinatra portfolio project to explain it.

The application is a mix between a social network where you can share content with other users and comment on what they share while having an punctuation system for each user. A user gets or loses points (karma) each time one of their post get upvoted or downvoted by other users.

## The Basic structure

As with any project the first thing to do is create the basic structure to keep all the code organized and make it follow a pattern that is easy to maintain.

![img](https://imgur.com/Yr3AdqT.jpg)

This structure helped me preserve a MVC application. As you can see, the actual code of my application is kept in the “app” folder. Controllers, Models and Views will interact with each other so this is an intuitive way to keep and eye on each of those interactions. 

## From the ground up

Many developers like to start the development process from what the user actually see and follow the flow of the application all the way to the database, this is by all means feasible and commonly used, but for this exercise I started to build from the database.  I did this to show how the process goes the other way around since sometimes a developer may come across a preexisting data source and there is little room to change how the models where created so the rest of the application has to accommodate this structure.

![img](https://imgur.com/tLSK58P.jpg)

As you can see, I created four migrations that will serve as de base of the models used in the application.

Once the migrations where in place, I filled my gemfile with what I would need for the rest of the project:

![img](https://imgur.com/dsuPsLq.jpg)

An important part in the development process is to identify what each member and each component should do. For this purpose, I created four branches in git to distribute the workflow.

![img](https://imgur.com/EnrHUxN.jpg)

With every thing in place, I continued to create the models in the application. Once the models where in place the rest of the pieces kind of fell in place one after another; going from controller to view then using what each of the models had to offer while getting the added functionality that active record offers.

## The models

As you can see in the following images, each model represented an object and the properties each of them had and how they interact with each other; that is, a user has many post, a post has many comments, comments belong to a post, votes belong to posts an users:

![img](https://imgur.com/a9wlBM0.jpg) 

```ruby
class User < ActiveRecord::Base
  include Slugify::InstaceMethods
  extend Slugify::ClassMethods
  has_many :posts
  has_many :votes , through: :posts
  has_many :comments
  has_secure_password
end

class Post < ActiveRecord::Base
  include Slugify::InstaceMethods
  extend Slugify::ClassMethods
  belongs_to :user
  has_many :comments , :dependent => :destroy
  has_many :votes, :dependent => :destroy
end

class Comment < ActiveRecord::Base
   belongs_to :user
   belongs_to :post
end

class Vote < ActiveRecord::Base
   self.primary_keys = :user_id, :post_id
   belongs_to :user
   belongs_to :post
end


```

## The views

I made the views in embedded ruby (ERB) which allowed me to interpolate ruby code and html for extra functionality.

The following images show the code and the actual view of the application’s index page.

![img](https://imgur.com/YS8SnuU.jpg)

![img](https://imgur.com/DGuQo0D.jpg)


## The controllers

Each of the controllers preserved the functionality of each of the models they managed; for example, the comments controller managed how comments were created, edited and deleted.

![img](https://imgur.com/ng9Z9ld.jpg)

![img](https://imgur.com/wErE2XR.jpg)

## Conclusion

In the end I’m very satisfied with how the project turned out. It showcases the basis of a CRUD application and I learned a lot about relationships between objects. 

If you wish to see a video a little more detail or the repository of the whole project, you can follow these links;

[Video](https://youtu.be/NLnQQMQ-CLA)

[GitHub Repository](https://github.com/jljardon/boarditt)






