## Coding course
The following document outlines the material of a course held for non-technical colleagues at WirelessCar. We will be going through the excercises and information below &mdash; take your time, it's better to understand than to rush through!

*Any text in italics provide some extra information as we go through the exercises &mdash; it may not be important to the task, but it will give some further context!*

# Setting up Python
We will be using the programming language Python in this course because it is easy to get started with. To save some time, we recommend that you download Python and a text editor beforehand.

You can download Python here: https://www.python.org/; check the Download tab to find your operating system.

For a text editor, we suggest that you download Visual Studio Code from here: https://code.visualstudio.com/Download

*You can use any text editor, but proper tools and software can help point out errors in your code, much like a spell-checker aiding you in Microsoft Word. Tangentially, Microsoft Word is **not** a text editor and is unfit for programming.*


# Hello World!
It has been tradition, at least since the famous 1978 book The C Programming Language, for new programmers' first program to output the phrase "Hello, World!". This is how you do it in Python:
```python
print('Hello, World!')
```
The "Hello, World!" program above has two parts: The `print` function and the provided parameter, `'Hello World'`.

There will be many short code examples in these exercises. We encourage you to try to run them yourself as you read along!

## Exercise 1
Make sure you can run the above code either on your computer or in the browser. Either way, you should have an editor window into which you can copy your code and a button to actually run your code, which will output program results to a secondary window. Follow the instructions in "Setting up Python" above, and ask us for help if you need it!

## Excercise 2
Instead of the program outputting "Hello, World!", modify it so that it instead says hello to you! E.g., "Hello, Alice!".

## Excercise 3
Extend the program to also say something about the weather on a new line, e.g., "Nice weather today!".

**Tip:** Nothing stops you from adding more `print`s to your code.

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

You may think of variables as labeled boxes that hold a single thing. The expression `x = 1` can be thought of as "put the value `1` into the box named `x`".

The equals sign does not have quite the same meaning as in mathematics. For example, the following expression is mathematically invalid but perfectly acceptable in Python:
```python
x = x + 1
```
## Exercise 4
What do you think the expression means? Write some code to test your hypothesis (`print` is your friend!).

# Lists
So far, we have used two *types* of values: `int`, short for integer (whole number); and `str`, short for "string", text. Now we get a third: `list`s!
```python
fruits = ['Apple', 'Banana', 'Tomato', 'Chickpea']
number_of_fruits = len(fruits)
print(f'There are {number_of_fruits} fruits')
print(f'The fruits are: {fruits}')
```
Here, `len` is a *function*, similar to `print`, that gets the length of a list.

*Most programming languages have strings, integers, lists, and functions. However, the details of how you write them (the syntax) and how they work (the semantics) vary. In java for example, `'` is used for single characters while `"` is used for strings*


## Exercise 5
What do you think will be the output when running the following program?
```python
mystery = len([])
print(f'{mystery}')
```

## Exercise 6
We can get a specific element from a list as follows:
```python
fruits = ['Apple', 'Banana', 'Tomato', 'Chickpea']
print(f'One of the fruits is {fruits[1]}')
```
What do you think this program with output? Try it! Did you get the result you were expecting? Why/why not?

## Exercise 7
Guess the output of this program! Check if you are right.
```python
fruits = ['Apple', 'Banana', 'Tomato', 'Chickpea']
removed = fruits.pop(1)
print(f'The removed fruit is {removed}')
print(f'The remaining fruits are {fruits}')
```

*Trivia: "Popping" is a programming term for taking an item from the end of a list. It comes from imagining a spring-loaded stack of plates (as you may find in a cafeteria). When the top plate is removed, the spring makes the stack "pop up", so the second plate takes the place of the first. In Python, the developer may optionally provide a number, denoting the index of the item in the list that they want removed. Have you found the quirk in how we tend to count in programming by now?*

## Exercise 8
What does the following program do?
```python
fruits = ['Apple', 'Banana']
fruits.append('Lemon')
print(f'Fruits: {fruits}')
```

## Exercise 9
Write a program that starts with the following line:
```python
fruits = ['Apple', 'Banana', 'Tomato', 'Chickpea']
```
The output of the program should be:
```
Strange fruits: ['Tomato', 'Chickpea']
```

<!--
```python
fruits = ['Apple', 'Banana', 'Tomato', 'Chickpea']
print(f'Strange fruits: {["Tomato", "ChickPea"]}')
```
-->

## Exercise 10
You can even put lists in lists! Guess what this program will output, and try running it:

```python
red_fruits = ['Tomato', 'Apple']
yellow_fruits = ['Banana', 'Pineapple']
all_fruits = [red_fruits, yellow_fruits]

print(f'One of the fruits is {all_fruits[1][1]}.')

```

Adjust the program above to instead output
`One of the fruits is Apple.`


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

## Exercise 11
What is the maximum number that `random.randint(0, 100)` could generate? `100`? `99`? Finding answers to these kinds of questions is an important skill in programming. Use your favorite search engine to find the answer!

## Exercise 12
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
Loops are a tool for running the same piece of code multiple times. There are multiple kinds of loops for different use cases such as running "once for each item in a list". We will stick to a basic kind of loop that run as long as some condition is met: `while`-loops. Lets look at an example:
```python
i = 0
while i < 2:
  i = i + 1
  print(f'i = {i}')
print('Done')
```
The execution of this program will go something like this:
1. Set `i` to `0`
2. Check if `i < 2`. It is (`i` is `0`), continue into the **loop body** &mdash; the indented part.
3. Set `i` to the previous value of `i`, plus `1`. So `i` is now `1`.
4. Output "i = 1". The end of the loop body has been reached, return to the beginning of the loop (line 2).
5. Check if `i < 2`. It is (`i` is `1`), continue into the loop body.
6. Set `i` to `2`.
7. Output "i = 2". Return to line 2.
8. Check if `i < 2`. It is not (`i` is `2`). Skip over the loop body.
9. Output "Done".

*Indentation is important in Python! Not indenting the loop body will result in your program not being able to run.*

## Exercise 13
Write a program using a `while`-loop that outputs the following:
```
1
2
4
8
16
```

## Exercise 14
Starting with our fruit list, write a program that outputs the fruits, one per line, in order.

## Exercise 15
Repeat exercise 2 but output the fruits in reverse order.

## Exercise 16
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
"Input" is a collective term for when a user provides any sort of information to a program. We will be providing text input to your running program. In Python, prompting a user for input is done as below:
```python
x = input("Type something here: ")
print(f"You wrote {x}")
```
When you run this program, it will wait until you provide some input. Write whatever you like and press enter to provide the written text as input.

## Exercise 17
Write a program that accepts user input three times and then outputs all the user provided input in a list.

# Random groups
Now we will tie all of the previous lessons together. You are going to build a program that can divide a number of people into groups of roughly equal size.

This could be useful if you ever find yourself in a situation where you need to divide your attendees in a meeting into breakout rooms, are deciding on teams on the after work for you and your colleagues, or similar.

We will build this step by step, starting from the problem specification. This is analogous to how we work as developers; when a problems need solving, we need to break down what is needed and what is possible with the tools you have, and make some assumptions that we challenge along the way.

## Excercise 18
Let's begin with building our list of people. Write a program that continuously asks the user to input a name until the user inputs "done". E.g., the output after a program has been run could look like:

```
Please enter a name: Victor
Please enter another name: Lukas
Please enter another name: done
You entered the names: ['Victor', 'Lukas']
```

**Tip:** Previously, we used the "less-than" operator (`<`) for a loop. You probably want to try out the "not-equal" operator `!=` this time. Also, note that the strings `"done"` and `"Done"` are *not* the same!

<!--
x = input("Please enter a name: ")
people = []
while x != "done":
    people.append(x)
    x = input("Please enter another name: ")

print(f"You entered the names: {people}")
-->

## Excercise 19
Now, let's start looking into the groups. Let's add some code after inputing a list of people that asks the user of how many people should be in a single group, and to pick out that many names at random from our "master list" of names to fill said group.

Let's start with creating one group for now and leave the rest of the names untouched.

**Tip:** You will likely run into trouble when trying to use the input number in this exercise: this is due to all variables you are using having a type, as mentioned in the *Lists* sections. Python is generally able to "guess" what you need, but when asking a user for input, the input will always be considered a string (text).

In order to convert a string to a integer, use the `int()` function:
```python
string_value = "5"
integer_value = int(string_value)
```

What do you think happens if you  use the `int()` function on a non-numerical string? Feel free to try!


<!--
group_size = int(input("Please enter group size: "))
first_group = []

while len(first_group) < group_size:
    first_group.append(people.pop(random.randint(0, len(people) - 1)))

print(first_group)
-->

## Exercise 20
 Finally, let's wrap up the program. Create not only one group, but as many groups necessary for the number of names given to the program. Make sure no one is left without a group! 
 
There are many ways one can do this, but in case you want to do some maths as part of your program, here is how: 

Maths is pretty straight forward in Python as long as you know the available operators. We have already shown examples of addition and subtraction as part of other exercises, and there is also multiplication with the `*` operator. The `/`  operator is used for division with decmals, while the `//` operator is integer division, which may be more relevant here:

 ```python
 x = 7 / 2
 y = 7 // 2

 print(x)
 print(y)
 ```

Here, `x` will be `3.5` while `y` will be `3`. As a side note, there is also the remainder operator `%` which calculates the remainder of a division, so `z = 7 % 2` will store the value `1` in `z`.

For the non-math inclined, don't worry -- this program is quite possible to write without multiplication or division.  

**Tip:** You may want to use a "list of lists" in this case to store all your groups.

**Tip:** Loops can be written in loops; might be useful here.

<!-- 
import random

x = input("Please enter a name: ")
people = []
while x != "done":
    people.append(x)
    x = input("Please enter another name: ")

print(f"You entered the names: {people}")

group_size = int(input("Please enter group size: "))
groups = []

print(group_size)
print(people)

while len(people) > group_size:
    i = group_size
    group = []
    while i > 0:
        person = people.pop(random.randint(0, len(people)-1))
        group.append(person)
        i = i-1
    groups.append(group)

groups.append(people)

loop = 0
while loop < len(groups):
    print(f"Group {loop+1}: {groups[loop]}")
    loop = loop + 1
-->

# Extra Credit 1:
Rewrite the program (you could save your first program as a separate file if you like to keep it) so that it will ask the user for the number of groups desired rather than group size, and divides the users accordingly.



# Finally

Three questions:
1. What was the most difficult thing today?
2. What was the most fun thing today?
3. A question about programming that you still want answered.
