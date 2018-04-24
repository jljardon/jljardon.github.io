---
layout: post
title:      "The importance of testing"
date:       2018-04-24 04:16:34 +0000
permalink:  the_importance_of_testing
---


A few years ago when I started my software development career I didn’t understand quite well why is important to follow Test Driven Development(TDD), as I began to get involved in larger and more complex projects I understood why testing is important and one of the best development practices and how it helps to speed up development time.

### What is Test Driven Development (TDD)?

TDD is an approach to software development in which a test is written for the functionality that we want to add before the actual code is written:

![TDD](https://i.imgur.com/ySsyFAZ.png)


First a test is written to verify that the code that will be implemented later meets the requested functionality. The developer runs the test to verify that it fails, then writes code (just enough) to satisfy the test’s requirements; runs the test again and if the test fails, the developer writes more code again, else the development cycle goes on to a new feature.

It may sound a bit complicated but I’ll try to explain it; lets say we want to write a test to check if a Student object can be created successfully and has a name attribute.

```
describe Student do

  before(:each) do
    @student = Student.new("Jose")
  end

  it 'can be created' do
    expect(@student).to be_valid
  end

  it "has a name" do 
    expect(@figure.name).to eq("Jose")
  end 
end
```

The test above requires a to create an Object of the Student class that has a name so the following code should be enough to make them pass:

```
class Student
  attr_accessor :name
  def initialize(name)
     @name = name
  end
end
```

If the code written is not enough to make the test pass or if the test still fails, the code should be modified again. This continues until the test passes and the developer can move to another feature or finish the development cycle.


### Why is TDD important?

TDD may seem unnecessary at first but it has many advantages that make it one of the best programming practices:

* Reduces time debugging
* Improves design
* Keeps code under control
* Promotes refactoring
* Speeds development
* Helps [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) and [KISS](https://softwareengineering.stackexchange.com/questions/73065/what-are-dry-kiss-solid-etc-classified-as)
* Reduces manual testing

In summary,  TDD helps the process of software development by producing code of better quality, reduces costs by improving development speeds and reduces risks by continually testing features, all of this makes it a requirement by most employers nowadays.

