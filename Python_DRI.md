
# Introduction to Python for Academic Researchers
<br><br>
## GCDRI June 7, 2016
## Michelle McSweeney 
## @MMcSweeney7
## \#GCDRI

### First Half Lesson Plan:
* Overview
* Variables & Types
* Conditionals 

~ Break ~ (*approximately*)


### Second Half Lesson Plan

* Loops
* Functions
* Psuedocode
* Libraries

Python is a **Language** that supports many **Packages**

### Packages

* NLTK (Natural Language Toolkit) for *Text Analysis*
* Pandas for *Data Analysis and Modeling* (DataFrames)
* Numpy for *High Level Mathematical Functions*
* MatPlotLib for *Making Graphs and Charts*


How do I know which one to use? 

*The Internet*

*Stack Overflow*

*Read the docs*

*Others doing similar work*

# Variables and Types

**Variables** are like a container for holding something

This can be helpful because:


* sometimes things are long:
    * my_file = open('/Users/michellejohnson/Documents/Spanish_English_BYTs.csv', 'r')


* sometimes you need a place to put something:
    * love_den = love_words/all_words


* sometimes you will just need a variable!

### Interactive Time!

* Open Anaconda (green guitar pick)
* Launch Notebook (will open in browser)
* New (at top right hand side of page)


To **run** a **cell** hit:
    
'Shift' + 'Enter'


```python
#setting my first variable

x = 8
y = 2
x+y

```


```python
z = x-y
print(z)
```

Some rules about **variables**
* NO SPACES
* Must be unique (unless you're overwriting something)
* Cannot be a command Python already uses, or is already used by a package (*we'll come back*)


```python
a = 3
b = 4
a = b
print('a is', a)
print('b is', b)
```

## Types
* Numbers
    * Integers
    * Floats 

## Types
* Strings "  " or ' ' *(this is so you can use apostrophes or quotes inside a string)*
    * usually words, always things Python can't "evaluate"
    * 'love'
    * 'Hello GCDI'

## Types
* Lists  [  ]
    * just like a shopping list
    * ['apples', 'bananas', 'kiwi']
    * [100, 200, 300]

## Types
* Dictionaries {  }
    * key:value  pair 
    * Keys are always unique - like your house key!
    * Values are not always unique...
    * Useful for counting instances of things
        * Let's say you are counting words: 
        * {'a':200, 'the': 500, 'at': 200}

## Types
**List** versus **Dictionary**
* List is ordered, Dictionary is not
* Lists allow look up by an **index**
* Dictionaries allow look up by a **key**
*More to come* 

## Types
*We are **not** covering these here*

* Sets 
    * Tuples(things grouped together, an unchangeable list)
    * Arrays (in Python, just use a list
* Texts (special (usually package-specific) type for words)
* DataFrame (specific to Pandas, like a spreadsheet or matrix)

### Type Examples

**Integers**


```python
n = 5
type(n)
```




    int



### Type Examples

**Floats**


```python
m = 5.1
type(m)
```




    float



### Type Examples

**Strings**


```python
str1 = 'Hello'
str2 = 'GCDRI'
print (str1)
print(str1, str2)
```


```python
str3 = str1 + str2
print(str3)
```


```python
str4 = str1 + ' ' + str2
print(str4)
```

### Type Examples

**Lists**

*Just like a shopping list* 


```python
my_list = ['apples', 'spinach', 'tofu']
print(my_list)
```


```python
my_list.append('rice')
print(my_list)
```


```python
my_list[1]
```

### Type Examples

**Dictionaries**


```python
my_dict = {'steak': 2, 'potatoes': 5, 'salad': 6}
print(my_dict)
```


```python
my_dict.items()
```


```python
my_dict.keys()
```


```python
my_dict.values()
```


```python
my_dict['steak']
```


```python
my_dict[2]
```

Why did that break?

**Keys** are **unique**

Values are not unique

Can only "call" or add items by their **key**



```python
my_dict['pie'] = 4
print(my_dict)
```

# Conditionals

aka "If-then statements"

Some style issues:
    * if item in my_list:
    * if a == b:
    * if a > b:
    * if a >= b:


```python
if students > teachers:
    print('Classroom')
if students < teachers:
    print('Conference')
if teachers == students:
    print('Private School')
```


```python
students = 60
teachers = 2
```

Let's check on our original list (my_list should still be an active variable in your program)


```python
print(my_list)
```


```python
if 'tofu' in my_list:
    print('Dinner time!')
else:
    print('You forgot my tofu!')
```

Three pieces of vocabulary for conditionals
    if _______:
    elif _________:
    else:


```python
if 'bagel' in my_list:
    print('Too many carbs')
elif 'tomatoe' in my_list:
    print('So healthy!')
```

What happened? Why didn't anything print?

What happens without the 'else' statement?

Challenge Question, this time, we'll play a game with Python.
We need another tool:
input 
*input is a way for Python to get information from a user.


```python
win = input('Pick the winning number: ')
guess = input('Player2, guess the number: ')
if win < guess:
    print('too high')
elif win == guess:
    print('you win!')
else:
    print('too low')
```

# For Loops


```python
#First, let's remember what was in my_list
print(my_list)
```


```python
for item in my_list:
    print("I'm gonna eat", item)
```

Now let's look at some numbers, we will put them in a new list

*there's a better way to do this, look up the function, range, if you regularly use lists of numbers in order*


```python
num_list = [1,2,3,4,5]
```


```python
for digit in num_list:
    print(digit)
    
```


```python
for digit in num_list:
    digit+=1

print(digit)
```

What does += do


Why did it only print 6??


```python
new_numb = []

for digit in num_list:
    new_dig = digit + 3
    new_numb.append(new_dig)

print(new_numb)
```

In regular language, what happened here?


Advanced For-Loops: Dealing with Dictionaries


```python
for item in my_dict:
    print("I'm gonna eat", item)
```

Why didn't it tell us how many of each? What did it return?'


```python
for item in my_dict.items():
    print("I'm gonna eat", item)
```

## Combining For-Loops and If-Statements!!


```python
fav_foods = ['watermelon', 'tofu', 'spinach', 'coffee']
```


```python
for food in fav_foods:
    if food in my_list:
        print('Yum', food)
    else:
        print('No', food, '?')
```

Now let's try it the other way to really get a sense of what is happening


```python
for food in my_list:
    if food in fav_foods:
        print('Yum', food)
    else:
        print('No', food, '?')
```

# Functions!

Functions are little bits of code that you can use over and over again.

* Python has some
* You can write some yourself
* You can import libraries of them
* You can borrow them from your friends!

**Functions** are **Fun!!**

Some vocabulary:

def _______(argument):
    some things i do
    what I give back

The **argument** is what the function will need to do its job. It's usually the little piece of information that your function operates on.



```python
#This function takes one argument and prints a greeting to the screen
#The argument is a string

def greet(name):
    print('Hello,', name)
    print('How are you?')
```


```python
greet('Wanda')
```


```python
greet('Floyd')
```

Now I want to greet both of them.


```python
greet('Wanda', 'Floyd')
```

Why did that break?

Let's try again


```python
greet('Wanda and Floyd')
```

**Another Tool!**

input() - a way to get information directly from your user



```python
x = input('What is your favorite number? ')
print('My favorite number is', x)
```

    What is your favorite number? 8
    My fav number is 8


Let's write a program to tell people how to write a book. 

Hint: This program will require using a Function!

Start with **pseudocode**


Wait! What's pseudocode???

Psuedocode is simplified code. 

* Articulate in words what you need the program to do


* Identify what you want to give it


* Identify what you expect to get back

* Identify the major steps


* Tackle each major step individually 
    * Worry about other steps later
    * Write out in words every tiny step
    * Test to see if the major step worked
    * Repeat this step
    
    
* Call your program

I want to write a program that gives people advice about how to write a book.
This program gets information from the user and tells them what they should do.

* Inputs: time & ideas
* Consider relationship between time and ideas, decide what advice to give
* Outputs: Advice

ideas = get number of ideas

time = get amount of time

Decide what advice to give:


* if they have less time than ideas, they should make time.

* if they have fewer ideas than time, they should get inspired.

* if the two are equal, they will probably write a book.


```python
#ideas = get number of ideas
all_ideas = input('How many ideas do you have? ')
#time = get amount of time
all_time = input('How much time do you have? ')
```


```python
def book(ideas, time):
    print('How to write a book')
    #if they have less time than ideas, they should make time.
    if time < ideas:
        print('Make time!')
    #if they have more ideas than time, they should get inspired.
    elif time > ideas:
        print('Get inspired')
    #if the two are equal, they will probably write a book.
    elif time == ideas:
        print("Can't wait to read it!")
    else: 
        pass
```


```python
#run program
book(all_ideas, all_time)
```


```python
#ideas = get number of ideas
all_ideas = input('How many ideas do you have? ')
#time = get amount of time
all_time = input('How much time do you have? ')

def book(ideas, time):
    print('How to write a book')
    #if they have less time than ideas, they should make time.
    if time < ideas:
        print('Make time!')
    #if they have more ideas than time, they should get inspired.
    elif time > ideas:
        print('Get inspired')
    #if the two are equal, they will probably write a book.
    elif time == ideas:
        print("Can't wait to read it!")
    else: 
        pass
        
#run program
book(all_ideas, all_time)
```

## Congratulations!! 

## You just wrote your first program!!

Now let's look at some built-in functions!

open( )  opens a file

read( )  reads the file

len( )   gets length of an object (i.e., string, list, dictionary, etc.)

Curious about all the built-in functions?

https://docs.python.org/3/library/functions.html

This is essentially what you are doing when you import a library.

Someone else already wrote all these little programs, and you are using them!

Three ways to import libraries:


* import csv - 'import' is a command, 'csv' is a package


* from csv import * - this says 'go to nltk and import everything' - save yourself and don't do this


* from csv import register_dialect



OMG! What's the difference??

**Something useful!!**

Now let's read in a csv file!


```python
import csv

f = open('/Users/michellejohnson/Desktop/pd_collections.csv', 'r')
my_file = csv.reader(f)

for row in my_file:
    print(len(row))
```

Now you are ready to specialize your programming skills through

* Cleaning Data 
* Analyzing Text
* Analyzing Numerical Data
* Making charts and graphs
* So much more!!

Now let's move to the **Command Line!!**

1. open a Terminal Window
2. Type the following command:

    $ python



3. Now you are using Python (to run a line of code, just hit 'Enter' not 'Shift'+'Enter'

4. Let's try it out with this simple program
    
    x = 'I love GCDI'

    len(x)
   


```python

```
