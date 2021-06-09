---
layout: post
title: Python Basics- Get them Intact
description: Only two days matter! The day you said ‘hello’ to the world and the day you printed ‘hello world’ in python. But we’re sure you wanted to say more than just a ‘hello’ to the world and wanted to print more than just ‘hello world’.
date: 2020-05-13
featured: no
---
We taught you how to set up the required python environment in the previous blog, if you haven’t read that, do give it a shot, else, you’ll have tough time setting it up on your own. We highly encourage you to not just read this blog but actually practice whatever we teach you by doing a hands on.

Let’s get our basics done. This part might feel a little boring but trust me this is very important, in fact it is a mandate, can’t skip.

Syntax Note- Python is a case sensitive language. Python takes indentation very seriously, indentation here represents a block of code. You’ll get loads of errors if you ignore the indentation.

Import the libraries
The two libraries that we’ll be using would be numpy and pandas, how to use import them?

Import them!
{% highlight python %}
import pandas as pd
import numpy as np
{% endhighlight %}

Variable
You would need to store data, loads of it, quite frequently. You’ll be using variables for that.

Assigning Value to a variable
Assign by hard coding
a=10
flag=true

Input Data
How do we input data from the user? Use this syntax
input(“Enter data- “)

Conditions
You’ll encounter multiple instances throughout your journey where you’ll have to make some decisions, decisions that are based on some conditions. Well, we can do this with python as well.

Syntax-
if condition
Condition 1’s result
elif
Condition 2’s result
else
Default result

Mangoes = 15
Bananas = 20
if Bananas > Mangoes-
print(“There are more Bananas than Mangoes“)
elif a == b-
print(“The no. of bananas and mangoes is equal“)
else -
print(“There are more Mangoes than Bananas“)

Arrays
Heard of lists, call them arrays from now. An Array is basically a list of values referenced under single name.

Syntax for assigning value- arrayName = [value1, value2, value3, …. , valuen]
So instead of using
firstPlayer = Player1
secondPlayer = Player2
thirdPlayer = Player3
Use
player = [Player1, Player2, Player3]

Know length of an array, you can do this by typing len(arrayName)
So, len(player) will give 3 as output

Loops
You would encounter situations wherein you’ll have to print lot of repetitive stuff like a count from 1 to 100 or print something hundred times. We use loops for that. You can learn more about and types of loops from the official python documentation.

The below code prints counting from 0 to 99 in 4 lines of code.
i = 0
while i<100 -
print(i)
i += 1

What if you had a list say, myList = [“First”, “Second”, “Third”] and you wanted to print all the elements of the list? Loops make this task easier. We use a for loop to demonstrate how this works

for var in myList-
print(var)

Output-
First
Second
Third

What if you wanted to print something through a loop but add some conditions at the same time?

myList = [“First”, “Second”, “Third”]
for var in myList-
if var!=”Second”-
print(var)

Output-
First
Third

You can learn more properties/functions of arrays, loops, conditions at https-//wiki.python.org/moin/BeginnersGuide/NonProgrammers, after all, we at Analytics Bay want to make you self-sufficient to survive in this world of Analytics.