---
layout: post
title:      "Basic control flow with IF statement"
date:       2018-01-19 02:14:43 +0000
permalink:  basic_control_flow_with_if_statement
---


The flow control of a computer program refers to the way in which the program itself has control to execute certain statements based on conditions that happen within its execution. In other words, the program has control over the decisions that it may have to take in its own execution.

A clear example of this would be buying a soda from a vending machine seen as a simplified sequence:

* Validate money – check `if` enough money was inserted. 
* Validate drink availability – check `if` there is at least one drink of the selected type in the machine.
* `if` the past two conditions are met, the product is dispatched.
* `if` the money inserted was more than the actual price of the drink, then return change (this one is tricky, because the machine has to check if there’s enough change before the humans select their drink, otherwise if no change is returned you get one upset human).

In a more concrete approach, most programming languages come with tools to simply guide the decisions the program makes along its execution.

### Enter the IF statement 

Simply put, the if statement shapes the decisions a program makes given certain conditions are met: 

```
if condition
   ex_this
elsif condition2
   ex_that
else
   do_something_else
end
```

The lines above show the basic flow an if statement follows but just to clarify here is an example of how it works:

```
if name == "Jay"
   puts "Hello, Jay!"
elsif name == "Matt"
   puts "Hi!"
else
   puts "I don't know you"
end
```

The previous if sentence will greet a person depending on the value of the name variable. That is, it’ll write “Hello, Jay!” if the value in the variable is “Jay”, if the name is not Jay, the program will check to see if the name is Matt, if the name is not mat, the program will finally say that it doesn’t know you.

The example above is quite simple; but it can be applied to a number of things where a program requires to decide which action to take. In the case of the vending machine:

```
if !enough_change?
   puts "Please insert exact change"
elsif enough_money? && drink_available?
   dispatch_drink
   return_change
else
   puts "Not enough money or that selection is not available, please try again"
end
```

The lines above will check first if enough change is available, if not it’ll write to insert exact change. Then if enough money was inserted and the drink is available it’ll dispatch the drink and return change, otherwise it’ll show that the operation was not completed.

Although it can be greatly improved, the vending machine example shows that given a situation follow the instructions that best serve its purpose.

There are other ways to control the flow of a program like loops but for now my objective was to explain in a simple manner why control flow in a computer program is important and the basics of it using the if statement. 


