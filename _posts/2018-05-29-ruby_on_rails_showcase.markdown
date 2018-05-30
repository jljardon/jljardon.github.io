---
layout: post
title:      "Ruby on Rails showcase"
date:       2018-05-30 01:03:34 +0000
permalink:  ruby_on_rails_showcase
---

---

Learning a new framework is always fun, and depending on how well designed and stablished is a framework, it may be a lot of work too. Fortunately for developers learning rails, it can be a really pleasant surprise the versatility and robustness that rails has. Rails as a Model-View-Controller(MVC) application tool is easy to learn, flexible and in many ways self explanatory since you can implement a CSS framework on top of it with ease along with the utilities that Active Record brings.  So to illustrate all this features, I built on the concept of another content management system I previously worked on.


## Structure
![](https://imgur.com/Mo0CCeY.jpg)

Using the command above, rails creates the basic structure of the app.



## Dependencies
Depending on the type and the features the app requires, it’s important to add gems and a CSS framework.

![](https://imgur.com/dxJae1f.png)


Although it wasn’t a requirement, I wanted to implement a CSS framework other that bootstrap; so I tried using Bulma.io. and it wasn’t that hard to implement.

![](https://imgur.com/AiDJfvJ.png)


![](https://imgur.com/Hg7TlLe.png)


## Models and Tables
I started creating the models that would be used by the application. In this case, it was required to create different types of relationships between the models (belongs to, has many and has many through). The details of said relationships can be found in the GitHub link the end of this post.

![](https://imgur.com/IEobMNR.png)


## Login and Sessions
To implement a login feature, I used OmniAuth strategies for Facebook and Google. The other option that the user has is to create an account that has certain validations from the model, like certain fields not being empty and having a unique username. Once the user creates an account, at the moment of login, a session is created using the users ID.

![](https://imgur.com/WDEJUYC.png)

![](https://imgur.com/4xZ72nL.png)




## Controllers and routes
The routes used are nested in two level for users posts and comments that belong to a post. And the controllers use strong parameters to persist information to the database and helpers to DRY the application and keep the business logic at a minimum.

![](https://imgur.com/eIFkxuB.png)


## Conclusion
Overall, I’m satisfied with the project. It shows what rails can do with ease, how to build new functionality on top of it and why it is one of the most widely used frameworks for web development.

You can find the complete project here:

https://github.com/jljardon/boarditt-rails







