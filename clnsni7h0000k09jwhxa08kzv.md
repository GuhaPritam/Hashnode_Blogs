---
title: "Python(Part - 2):Unlocking the Power of Python Variables"
seoTitle: "Python(Part - 2):Unlocking the Power of Python Variables"
seoDescription: "Dive into Chapter 2 of 'Python for Beginners' to unravel the power of variables, a fundamental concept in Python programming."
datePublished: Mon Oct 16 2023 08:46:13 GMT+0000 (Coordinated Universal Time)
cuid: clnsni7h0000k09jwhxa08kzv
slug: unlocking-the-power-of-python-variables
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1694414102932/ab7eb4ee-9315-4943-ad0b-524809ebe446.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1694516941876/2463b9af-754d-4c97-b8f7-f03ceef51099.png
tags: software-development, python, development, developer, python3, coding, devops, functional-programming, software-engineering, scope, pythonvariables, global-variables

---

## `Introduction :`

A variable is a type of container that stores values. You don't need to declare variables before using them or before declaring their type. Without assigning any values, the variable is completely useless. When we assign any value to a variable, it will take a memory location.

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text">You can assign a variable to a different value or data type. Python allows variables to change their values during runtime.</div>
</div>

## `Rules for Python variables:`

* The variable name should be `meaningful`. Because of your program, you can easily remember and use that variable.
    
* The variable name shouldn't start with a `number`.
    
* The variable names are case-sensitive (`pritam`,`Pritam`, and `PRITAM` are three different variables).
    
* In the variable name, you shouldn't use any`reserved words` (if, else, while, for, def, import, class, etc.).
    
* Python follows the`"snake_case"` convention for naming variables. In this case, the variable names are followed by `lowercase letters` and `words are separated by underscores` (pritam\_guha, user\_name, python\_variable, etc.).
    
* When we declare any variable name, we should follow the `global` and `local scope` rules.
    

### `Examples:`

```python
# valid variable name
pritam = 1
Pritam = 2
Pr_it_am = 3
_pritam = 4
pritam_ = 5
_PRITAM_ = 6

print(pritam, Pritam, Pr_it_am)
print(_pritam, pritam_, _PRITAM_)
```

### `Output:`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694426483251/9d5b56dc-5794-477a-b05b-af9aee2bb598.png align="left")

## `Example 1:(Associating Names with Values)--`

Here we assigned some values to some variables. There is a number, a floating-point number, and a string.

```python
# Integer
age = 26
# Floating point
salary = 1234.8
# A string
name = "Pritam"

print("age -- ", age)
print("salary -- ", salary)
print("name -- ", name)
```

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text"><code>"age -- "</code>This is a string literal enclosed in double quotes. It's a piece of text that you want to display as part of your output.</div>
</div>

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text"><code>age</code>This is the variable<code>age</code> that you declared earlier. When you include it as an argument to<code>print</code>, it displays the value associated with the <code>age</code> variable.</div>
</div>

### `Output:`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694499796166/999ad989-00d8-42b2-820c-47d1d152f1d6.png align="left")

## `Example 2:(Reassignment of Variables in Python)--`

Python allows variables to dynamically adopt new values during program execution. In this case, we re-assigned the values in the same variable.

```python
# declaring the variable
Number = 100
# See the value
print("Before declare: ", Number)

# re-assigned the variable
Number = 120.3
print("After re-assigned:", Number)
```

### `Output:`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694499759825/3dc5327c-7e99-44e4-81c1-4b02c633370d.png align="left")

## `Example 3:(Multiple Variable Assignment in Python)--`

Python allows assigning a single value to several variables continuously with the “=” operator.

```python
a = b = c = d = e = 20

print("[ Info ] -- ", a)
print("[ Info ] -- ", b)
print("[ Info ] -- ", c)
print("[ Info ] -- ", d)
print("[ Info ] -- ", e)
```

### `Output:`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694500901806/e259b66a-7cd0-4755-a9b7-69c1e544d9b5.png align="left")

## `Example 4:(Using Variables in Mathematical Expressions)--`

Variables are valuable in mathematical calculations. Here are some examples.

```python
length = 5
width = 3
area = length * width

print("Area -- ", area)

a = 10
b = 20
add = a + b

print("Add -- ", add)

a = "Pri"
b = "tam"
name = a + b

print("Name -- ", name)
```

### `Output:`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694501620090/778f8ac6-9e99-453c-90f7-58f1fae55932.png align="left")

## `Example 5:(Global and Local Python Variables)--`

In Python, variables can have different scopes, meaning they can be accessible in certain parts of your code but not in others. The two most common types of variable scopes in Python are global and local.

> **I've already created a blog related to this. Please visit that blog.**

[Click Here ---&gt;](https://pritamguha.hashnode.dev/what-is-function-scope)

## `Example 6:(Variable Naming Conventions: Pascal Case, Camel Case, and Snake Case)--`

Explore the different variable naming conventions used in programming. Learn about Pascal case, Camel case, and Snake case and how they impact code readability and style.

```python
NameOfCity = "Mumbai"  # Pascal case
nameOfCity = "Berlin"  # Camel case
name_of_city = "Moscow"  # Snake case

print("Pascal case -- ", NameOfCity)
print("Camel case -- ", nameOfCity)
print("Snake case -- ", name_of_city)
```

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text">In Python, the naming convention that is used most frequently is <strong>snake_case</strong>.</div>
</div>

### `Output:`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694523137841/0192db2c-7d3c-46b0-93be-8d9ddf5975d1.png align="left")

%[https://www.pritamguha.com/] 

%[https://github.com/GuhaPritam] 

%[https://youtube.com/@codeplayer-3828?si=HoSahYy9Q8t6Jfrt]