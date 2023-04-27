## Coding course
The following document outlines the material of a course held for non-technical colleagues at WirelessCar. We will be going through the excercises and information below -- take your time, it's better to understand than to rush through!

*Any text in italics provide some extra information as we go through the exercises -- it may not be important to the task, but it will give some further context!*

# Setting up Python
We will be using the programming language Python in this course because it is easy to get started with. To save some time, we recommend that you download Python and a text editor beforehand.

You can download Python here: https://www.python.org/; check the Download tab to find your operating system.

For a text editor, we suggest that you download Visual Studio Code from here: https://code.visualstudio.com/Download


# Hello World!
It has been tradition, at least since the famous 1978 book The C Programming Language, for new programmers' first program to output the phrase "Hello, World!". This is how you do it in Python:
```python
print('Hello, World!')
```

The "Hello, World!" program above has two parts -- the "print()" function and the provided parameter, which is 'Hello World'.

There will be many short code examples in these exercises. We encourage you to try to run them yourself as you read along!


## Exercise 1
Make sure you can run the above code, either on your computer or in the browser. Follow the instructions in "Setting up Python" above, and ask us for help if you need it!

## Excercise 2
Instead of the program outputting "Hello, World!", modify it so that it instead says hello to you! E.g. "Hello, Alice!".

## Excercise 3
Extend the program to also say something about the weather on a new line, e.g. "Nice weather today!".

**Tip:** Nothing stops you from adding more "print()"s to your code.

# Variables
Variables are names that we bind values to. For example, we can create three variables, `x`, `y`, and `sum` and output their values:
```python
x = 1
y = 2
sum = x + y

print(f'x: {x}')
print(f'y: {y}')
print(f'sum: {sum}')
```
To output the value of a variable, we can write its name within curly brackets in the string. We also need to prefix the string with `f` (for format), otherwise the output would be `sum: {sum}` instead of `sum: 3`.

You make think of variables as labeled boxes that hold a single thing. The expression `x = 1` can be thought of as "put the value `1` into the box named `x`".

The equals sign does not have quite the same meaning as in mathematics. For example, the following expression is mathematically invalid but perfectly acceptable in Python:
```python
x = x + 1
```

## Exercise 1
What do you think the expression means? Write some code to test your hypothesis (`print` is your friend!).

## Exercise 2
In our goal to print the sum of `x` and `y`, you don't actually need the variable `sum`. Try making the program behave the same without it! 

*When it comes to programming, having less lines of code producing the same result is (usually) a good idea. We don't want to compromise on having the code readable by our colleagues, however!* 

# Lists
So far, we have used two *types* of values: `int`, short for integer (whole number); and `str`, short for "string", text. Now we get a third: `list`s!
```python
fruits = ['Apple', 'Banana', 'Tomato', 'Chickpea']
number_of_fruits = len(fruits)
print(f'There are {number_of_fruits} fruits')
print(f'The fruits are: {fruits}')
```

Here, `len` is a *function*, similar to `print`, that gets the length of a list.

*While strings, integers, lists and functions exist in most programming languages, languages differs in how to define them. For instance in Java, only double quotations denote a string. 
Such "rules" of a language is commonly referred to as the "syntax" of a language.*


## Exercise 1
What do you think will be the output when running the following program?
```python
mystery = len([])
print(f'{mystery}')
```

## Exercise 2
We can get a specific element from a list as follows:
```python
fruits = ['Apple', 'Banana', 'Tomato', 'Chickpea']
print(f'One of the fruits is {fruits[1]}')
```
What do you think this program with output? Try it! Did you get the result you were expecting? Why/why not?

## Exercise 3
Guess the output of this program! Check if you are right.
```python
fruits = ['Apple', 'Banana', 'Tomato', 'Chickpea']
del fruits[1]
print(f'The remaining fruits are {fruits}')
```

## Exercise 4
What does the following program do?
```python
fruits = ['Apple', 'Banana']
fruits.append('Lemon')
print('Fruits: {fruits}')
```

## Exercise 5
Write a program that starts with the following line:
```
fruits = ['Apple', 'Banana', 'Tomato', 'Chickpea']
```
The output of the program should be:
```
Strange fruits: ['Tomato', 'Chickpea']
```

# Randomness
So far, all our programs have produced the same result every time they are executed. Lets change that! We are going to use a *pseudorandom number generator*. Rather than writing one ourselves, which is a bit complicated, we are going to **import** the `random` module.
```python
import random

random_number_1 = random.randint(0, 100)
random_number_2 = random.randint(0, 100)

print(f'First random number {random_number_1}')
print(f'Second random number {random_number_2}')
```
Here, `randint` is just a function in the `random` module. The numbers, `0` and `100`, is the range that we want to pick a number from.

## Exercise 1
What is the maximum number that `random.randint(0, 100)` could generate? `100`? `99`? Finding answers to these kinds of questions is an important skill in programming. Use your favorite search engine to find the answer!

## Exercise 2
Write a program that outputs a random fruit.
<!--
```python
import random

fruits = ['Apple', 'Banana', 'Tomato']
number_of_fruits = len(fruits)
random_number = random.randint(0, number_of_fruits - 1)
random_fruit = fruits[random_number]
print('Your random fruit is %s' % random_fruit)
```
-->

# Loops

`while`-loops. Lets look at an example:
```python
i = 0
while i < 2:
  i = i + 1
  print(f'i = {i}')
print('Done')
```
The execution of this program will go something like this:
1. Set `i` to `0`
2. Check if `i < 2`. It is (`i` is `0`), continue into the **loop body** --- the indented part.
3. Set `i` to the previous value of `i`, plus `1`. So `i` is now `1`.
4. Output "i = 1". The end of the loop body has been reached, return to the beginning of the loop (line 2).
5. Check if `i < 2`. It is (`i` is `0`), continue into the loop body.
6. Set `i` to `2`.
7. Output "i = 2". Return to line 2.
8. Check if `i < 2`. It is not (`i` is `2`). Skip over the loop body.
9. Output "Done".

## Exercise 1
Write a program using a `while`-loop that outputs the following:
```
1
2
4
8
16
```

## Exercise 2
Starting with our fruit list, write a program that outputs the fruits, one per line, in order.

## Exercise 3
Repeat exercise 2 but output the fruits in reverse order.

## Exercise 4
Repeat exercise 2 again, but output the fruits in random order.

<!--
```python
fruits = ['Apple', 'Banana', 'Tomato', 'Chickpea']
while len(fruits) > 0:
  random_fruit = del fruits[random.randint(0, len(fruits) - 1)]
  print(f'{random_fruit}')
```
-->

# Input

# Random groups
Write a program that reads a list of names and randomly divides them into groups of roughly equal size.

TODO: Input from list/stdin? Names and number of groups


## Finally

Three questions:
1. What was the most difficult thing today?
2. What was the most fun thing today?
3. A question about programming that you still want answered.
