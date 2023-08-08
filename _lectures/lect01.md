---
num: "Lecture 1"
desc: "Introduction, Python Review"
ready: true
lecture_date: 2023-08-08 09:30:00.00-7:00
---

Recorded Lecture: [8_8_23](https://drive.google.com/file/d/1TbfH2GD9qyrQTFrDkACRuqJb5CKuc2Dr/view?usp=sharing)

* Course webpage: [https://ucsb-cs9.github.io/m23/](https://ucsb-cs9.github.io/m23/)
	* Please read and understand the syllabus: [https://ucsb-cs9.github.io/m23/info/syllabus/](https://ucsb-cs9.github.io/m23/info/syllabus/)

# Python Basics

* Python is an example of an interpreted language (unlike C/C++ and Java)
* Each line is interpreted one at a time
* Does have some flexibility, especially when simply running a program from top-to-bottom
	* But is also dangerous since it doesn’t check for type errors and may fail in the middle of execution
* Python interactive shell (IDLE) can execute lines of code by typing it in
* Stores state of variables that can be reused, BUT…
	* Once you exit the interactive shell, memory is cleared and your work is lost
	* So python programs are usually NOT written in the interactive shell and in separate .py files

# Python Buit-in Atomic Types

* Python has some basic types of data that come straight out-of-the-box
* Examples are integers (int) and floats (decimals)
	* May affect the output type you’re getting, even if it’s numerically the same

## Example

```
>>> 2/2
1.0 # float
>>> 2 + 2
4 # int
>>> 2 + 2.0
4.0 # float
```

* And there are certain functionality that may work with certain types, but not others

```
>>> x = 10.0
>>> int(x)
10
>>> float(x)
10.0
>>> x = "10.0" # string type
>>> type(x)
<class 'str'>
>>> x = float(x)
>>> type(x)
<class 'float'>
>>> x = int(x)
>>> type(x)
<class 'int'>
>>> x = "10.0"
>>> x = int(x)
Traceback (most recent call last):
  File "<pyshell#105>", line 1, in <module>
    x = int(x)
ValueError: invalid literal for int() with base 10: '10.0'
>>> len(x)
4
>>> len(float(x))
Traceback (most recent call last):
  File "<pyshell#107>", line 1, in <module>
    len(float(x))
TypeError: object of type 'float' has no len()
```

# Relational and Logical Operators

* Output of these operators result in a Boolean value
	* True , False
* Boolean values are important for control structures (while loops, if statements)
* Basically, allows you to fine-tune your program and define what / when instructions should be executed.

# Example

```
>>> 5 == 5
True
>>> 5 != 5
False
>>> 5 < 5
False
>>> 5 <= 5
True
>>> 5 > 4
True
>>> 4 >= 5
False
>>> True or False
True
>>> not False or False
True
>>> False and True
False
```

# Python Lists

* A dynamic collection of data (heterogeneous types) that can be indexed (index starting at 0).

## Example

```
>>> x = []
>>> len(x)  # returns number of elements in list
>>> x.append(1)	 # adds to the end of the list
>>> x
[1]
>>> len(x)
1
>>> x = [1,2,2,3,3,3]
>>> len(x)
6
>>> x[3]  # extracts an element at an index (index starts at 0)
3
>>> x[3] = "3"  # assigns a value at a certain index
>>> x
[1, 2, 2, '3', 3, 3]
```

* Data types can have methods (functions that can be called on an instance of a type (or object))

```
>>> x = [1,1,2,2,2]
>>> x.count(2)  # counts the number of times 2 appears in the list
3
>>> x.count(3)
0
>>> x = [1,'2',3,'4']
>>> '1' in x  # Returns True if '1' is in the list, False otherwise
False
>>> 1 in x
True
>>> x.insert(2, 2.5)  # inserts 2.5 in index 2 of the list, shifts right elements over
>>> x
[1, '2', 2.5, 3, '4']
>>> x.pop()  # removes and returns last element of list
'4'
>>> x
[1, '2', 2.5, 3]
>>> x.pop(1)  # removes element at index 1
'2'
>>> x
[1, 2.5, 3]
>>> del x[1]  # Notice that there isn’t any output, but still removes element
>>> x
[1, 3]
```

* Python methods and functions may or may not have a return value
* A special value (`None`) is used to represent a non-returned value
* It may be useful to store a return value to a variable, because once a value returns and is not stored, then it’s gone!

# List Slicing

* `[i:j]` syntax starts (includes) element at index i up to (not including) element at index j

## Example

```
>>> x[1:4]
[2, 3, 4]
>>> x[1:7]
[2, 3, 4, 5]
>>> x[1:]
[2, 3, 4, 5]
>>> x[:3]
[1, 2, 3]
```

# Strings

* Strings represent a collection of characters
	* But in python, characters aren’t a data type. It’s basically a string with one value
* Strings are very similar to Lists (not exactly though...)

## Example

```
>>> x = "CS9"
>>> type(x[2])
<class 'str'>
>>> x[2]
'9'
```

But...

```
>>> x[2] = "1"
Traceback (most recent call last):
  File "<pyshell#5>", line 1, in <module>
    x[2] = "1"
TypeError: 'str' object does not support item assignment
```

* Lists in Python are MUTABLE (can change the existing list)
* Strings are IMMUTABLE (cannot change the existing string)

## Some useful string methods

```
>>> x = x.replace("9", "1")  #returns a string,replaces the “9” with “1” in x
>>> x
'CS1'
>>> x.split("S")  # splits the string at the first occurrence of “S”
['C', '1']
>>> x.find("1")  # returns the index of the first occurrence of “1”
2
```