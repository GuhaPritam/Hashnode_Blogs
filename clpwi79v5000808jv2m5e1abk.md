---
title: "Python(Part - 3):Getting Started with Python Data Types"
seoTitle: "Python(Part - 3):Getting Started with Python Data Types"
seoDescription: "In programming, data types are like labels that tell the computer how to interpret and manipulate data. Data types are defined for all the variables."
datePublished: Fri Dec 08 2023 10:48:14 GMT+0000 (Coordinated Universal Time)
cuid: clpwi79v5000808jv2m5e1abk
slug: pythonpart-3getting-started-with-python-data-types
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1694429106154/ee04ad96-1fd9-471a-b2e1-3bda0a8cd13d.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1696078217897/1046354c-d416-4fac-bf6a-74fcfcfb7f6f.png
tags: variables, software-development, python, data-structures, fundamentals, developer, python3, coding, devops, beginners, software-engineering, boolean, dictionary, python-beginner, numerical-methods

---

## `Introduction:`

In programming, data types are like labels that tell the computer how to interpret and manipulate data. Data types are defined for all the variables. Data types are classes, and variables are instances. Every data type has another kind of feature.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696063707658/fac1a3e0-bbf8-4a7d-b94a-8a3e444165fe.png align="center")

## `Numeric Data type:`

In Python, numeric data types are used to represent numbers.

* `Integers (int):` Integers are whole numbers without a decimal point.
    
* `Floating-Point Numbers (float):` Floating-point numbers are numbers with a decimal point, and they're accurate up to `15` decimal places.
    
* `Complex Numbers (complex):` Complex numbers have both real and imaginary parts, denoted by `'j'`.
    

### `Examples:`

```python
age = 25
print(age, 'is of type', type(age))

temperature = -5.5
print(temperature, 'is of type', type(temperature))

num3 = -1 - 4j
print(num3, 'is of type', type(num3))
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696064486917/8a6e0428-6918-4f6b-aeac-6531a7f8a324.png align="left")

## `Dictionary Data Type:`

In Python, a dictionary is a type of data type that stores a collection of key-value pairs. Each key in a dictionary is unique, and it is used to store a value of that variable. Dictionaries are also known as "dict" and are represented using curly braces {}. A Python dictionary is an ordered collection of items.

You can create a dictionary by enclosing a comma-separated list of key-value pairs within curly braces`{}`. Each key is separated from its corresponding value by a colon `:`.

To access the values in a dictionary, you use the keys as indexes.

### `Examples:`

```python
# Creating a dictionary
my_dict = {
    "name": "Pritam",
    "age": 30,
    "city": "India"
}

# Accessing values
print(my_dict["name"])
print(my_dict["age"])
print(my_dict["city"])
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696066073340/c228427e-86d0-4f8d-80c4-0f1e1b215dd3.png align="left")

## `Boolean data type:`

In Python, the Boolean data type represents truth values. It has only two possible values: True and False.

### `Examples:`

```python
x = 5
y = 10
print(f"Returns False as x is not equal to y -- {bool(x==y)}\n")

x = None
print(bool(x))
print(f"Returns False as x is None -- {bool(x)}\n")

x = ()
print(bool(x))
print(f"Returns False as x is an empty sequence -- {bool(x)}\n")

x = {}
print(bool(x))
print(f"Returns False as x is an empty mapping -- {bool(x)}\n")

# Returns False as x is 0
x = 0.0
print(bool(x))
print(f"Returns False as x is 0 -- {bool(x)}\n")

x = 'Pritam Guha'
print(bool(x))
print(f"Returns True as x is a non empty string -- {bool(x)}\n")

x = (10 > 9)
print(bool(x))
print(f"Returns True as x condition is right -- {bool(x)}\n")

x = (10 < 9)
print(bool(x))
print(f"Returns False as x condition is wrong -- {bool(x)}\n")
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696070307058/e1d62c86-4296-4d52-bbca-1b49dbb6a9f0.png align="center")

## `Set data type:`

A Set is a data type that represents an unordered collection of unique elements. Sets are defined using curly braces {} or the set() constructor function.

Sets are used to store multiple items in a single variable.

In Python, there are four fundamental built-in data types designed for storing collections of data. These include Lists, Tuples, Dictionaries, and Sets.

### `Examples:`

```python
set_1 = {"apple", "banana", "mango", "apple"}
print(f'\nDuplicate values will be ignored -- {set_1}')

set_2 = {"apple", "banana", "mango", True, 1, 2}
print(f'\nTrue and 1 is considered the same value -- {set_2}')

set_3 = {"apple", "banana", "mango"}
print(f"\nLength of set_3 -- {len(set_3)}")
print(f'True and 1 is considered the same value -- {set_3}')

set_4 = {"abc", 25, True, 60, "male"}
print(f'\nA Set can store different data types -- {set_4}')

set_5 = {"apple", "banana", "mango", "apple"}
print(f'\nUsing set() to make a Set -- {set_5}')
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696072046734/b00a9e39-e9b0-4fc3-8f38-d53385aa2b4f.png align="center")

## `Sequence data type:`

The Sequence Data Type in Python is an ordered collection of similar or different data types. This Data Type has List, String, Tuple, and Byte Sequence Data Types.

* `Lists (list):` Lists are ordered collections of items that can be of many types of data.
    
* `Tuples (tuple):` Tuples are similar to lists, but their elements cannot be changed after creation.
    
* `Strings (str):` Strings are sequences of characters and are used to represent text.
    
* `Byte Sequences (bytes and byte array):` These are used to represent binary data.
    

### `Examples:`

```python
my_list = [1, 2, 3, "apple", "banana"]
print(f'\nThis is a List -- {my_list}')

my_tuple = [1, 2, 3, "apple", "banana"]
print(f'\nThis is a Tuple -- {my_list}')

my_string = "Hello, Pritam!"
print(f'\nThis is a String or Text -- {my_list}')

my_bytes = b'binary data'
my_bytearray = bytearray(b'editable binary data')
print(f'\nThis is a Byte -- {my_bytes}')
print(f'This is a Byte Array -- {my_bytearray}')
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696073416166/6d71eb9b-1ac7-41ab-b1d7-42a8d75b1821.png align="center")

%[https://www.pritamguha.com/] 

%[https://github.com/GuhaPritam] 

%[https://youtube.com/@codeplayer-3828?si=HoSahYy9Q8t6Jfrt]