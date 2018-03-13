---
layout: post
title:      "Object Relational Mapping"
date:       2018-03-13 02:09:26 +0000
permalink:  object_relational_mapping
---


When developing and application, most of the time, we’ll come across the necessity to use a database to persist the data that is important for the program. For this task we could always use SQL statements directly manipulating our database and finding information, but most of the time, it’s better to use a mapping tool(**Object Relational Model**) that will simplify the process and improve our development time while keeping our application reliable.

## What is ORM?

ORM is a technique that serves as an interpreter between an object oriented programming language such as Java, Ruby, C#, etc.  and a database management system(DBMS). This helps the programmer deal with SQL statements in a more structured and organized manner using “mapping” that otherwise would become very confusing very fast if developed individually for each of the objects in an application.
 
Although ORM is a technique for modeling database tables into objects, most people refer to “ORM” as a library or framework that implements maps for the objects we create.

## Advantages of an ORM system

* Lets the controller code of an application have access objects instead of using plain SQL to communicate with the database.
* Simplifies code; once the code for the model is written, said code is easier to maintain and reuse.
* Keeps the details of SQL queries outside of the main flow of the program, making it more readable.
* Automated of SQL queries
* Enforces the use of MVC and good development practices.
* Speeds up development time
* Homogenized syntax; only the OOP language is needed and the ORM takes care of the rest.


## Disadvantages

* Most ORMs tend to be a bit heavy and have way more functionality that a small application will use.
* Learn it. ORMs sometimes use specific syntax
* Requires being careful of un using huge CRUD statements inside loops or similar constructs.

## Examples

The following code shows a few functions that use Active Record in ruby to simplify CRUD statements in a Movie model:

```
class Movie < ActiveRecord::Base

end
```


**Creating a record:**


```
def can_be_instantiated_and_then_saved

   movie = Movie.new

   movie.title = 'This is a title.'

   movie.save

end
```


**Getting last record in the movie table:**

```
def can_get_the_last_item_in_the_database

   Movie.last.title

end
```

**Find a record by id:**

```
def can_find_an_item_from_the_database_using_id

   Movie.find_by(id: 1)

end
```

**Find a record by multiple attributes:**

```
def can_find_by_multiple_attributes

   attributes = { title: 'Title', release_date: 2000, director: 'Me' }

   Movie.find_by(attributes)

end
```

**Update and save a record:**

```
def can_be_found_updated_and_saved

   Movie.create(title: 'Awesome Flick')

   movie = Movie.find_by(title: 'Awesome Flick')

   movie.update(title: 'Even Awesomer Flick')

   movie.save

end
```

**Delete a record:**

```
def can_destroy_a_single_item

   Movie.create(title: 'That One Where the Guy Kicks Another Guy Once')

   movie = Movie.find_by(title: 'That One Where the Guy Kicks Another Guy Once')

   movie.destroy

end
```




