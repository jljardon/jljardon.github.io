---
layout: post
title:      "Basic flow control Part II - Loops"
date:       2018-02-04 07:33:11 +0000
permalink:  basic_flow_control_part_ii_-_loops
---


Last time I explained how the `if` statement was important to determine the flow of execution in our code. This time I would like to talk about loops, which are another way to control our programs.

## What is a loop?

A loop is the repetition of a segment of code given a certain number of times or until a condition is met. There are several kinds of loops: `while`/`until`, `do`/`while` and `for`. The purpose of a loop is to simplify the code by not repeating statements, methods or other kinds of actions; and although the function of each type is more or less the same, they can be used to simplify our code in different ways.


## A simple loop

When we write a loop the first thing we need to consider is how many times we want to execute the code inside said loop. For example, the next loop writes hello 5 times to console:

```
5.times do
	puts "Hello"
end  
```

This kind of loop may help in case we need to write a segment of code a given number of times but more often than not the easiest way to control a loop is with a counter. The next loop subtracts from 10 to 0 and sends the output to the console:

```
counter = 10
while counter >= 0 do
	puts "#{counter}"   
	counter -=1   
end  
```

We can execute any type of sentence inside a loop but we may come across a situation when we need to exit said loop if a condition is met, in that case we can use `break` inside the loop, however it is advised to analyze the condition properly since some times this will yield an unexpected result:

```
counter = 10
while counter >= 0
	if counter == 7   
		puts 'The loop will now exit'      
		break      
		puts 'This will not be executed'      
	end     
	puts counter.to_s   
	counter -= 1   
end  
```

As you can see in the code above, the `puts` bellow the `break` statement will never be executed since the loop will exit every time before getting to that instruction. 

Another way we can control a loop is using `next`. This helps if we want to skip the immediate section of our program. The following code prints the current value of the counter but skips printing 3 due to the `next` statement:

```
counter = 0
loop do
	counter += 1   
	next if counter == 3   
	puts "counter: #{counter}"   
	break if counter == 5   
end  
```



## Types of loops

As I said before, there are different types of loops that work in a similar way but with some conditions is better to use one or the other.

### While loop

A while loop is executed until a condition given to the loop is met. The following while loop sums 2 to its counter while the counter is less than or equal to 100:

```
counter = 0
while counter <= 100
	puts counter  
	counter +=  2  
end  
```


### Until loop

Very similar to the `while` loop but helps to express ideas in a different way more similar to a human expression. The following code has identical output to the previous segment but when read aloud the objective is a bit clearer (sums counter until it is equal to 100):

```
counter = 0
until counter == 100
	puts counter  
	counter +=  2  
end  
```

### For loop

This loop is used in ruby to go over a collection. The main difference of this loop with the rest is that it’ll return the collection it went over:

```
counter = (1..10).to_a   
for j in counter do   
	puts j      
end
```

The past segment of code will return an `array` with the values 1 to 10 but it will also print the values of the `j` variable. This particular loop helps to operate over a collection while also being able to modify its contents.

### Do/While loop

The `Do/While` loop is similar to the `while` loop with the difference that regardless of the condition it will execute at least one time:

```
loop do   
	puts 'The loop will end only if exit is typed'      
	input = gets.chomp      
	break if input.downcase == 'exit'      
end
```

The above code will display its message and will continue to do so until the user types “exit”.

## Conclusion

The purpose of this post was to show the basics of a loop and its function within a program. As you can see loops are an essential part of programming and not only to simplify our code by getting rid of repetition that we would have to go through without them, but they also help to express our ideas clearly and efficiently.	

