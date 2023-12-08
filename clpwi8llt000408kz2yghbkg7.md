---
title: "Best approach to write efficient code
in Python"
seoTitle: "Best approach to write efficient code
in Python"
datePublished: Fri Dec 08 2023 10:49:16 GMT+0000 (Coordinated Universal Time)
cuid: clpwi8llt000408kz2yghbkg7
slug: best-approach-to-write-efficient-code-in-python
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1696241784909/247c4850-57b0-46f1-9ea2-7824a37fb5ad.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1696241826890/54d17220-89f1-486f-8a58-f166283c853e.png
tags: python, python3, coding, python-beginner

---

## `Introduction:`

Python is known for its readability and simple of use, but it's also important to write efficient code to ensure your programs run quickly and consume minimal resources.

With this, we should remember which code will take time and memory. If we can reduce the time and memory needed to compile any code, that will be perfect for approaching the best logic.

Below are some examples to make your work more perfect.

* Try to create `functions`.
    
* Decrease useless `operations`.
    
* Do not declare `variables` that are not necessary.
    
* Reduce your `if-else` conditions.
    
* Replace `time with sleep` to `wait until`.
    
* The loops should be `broken` as needed.
    
* Avoided the `global variables`.
    
* convert all the big `if-else` conditions to `switch-case` statements.
    
* Use `Generators` for large `Data Sets.`
    

# `1. Creating meaningful functions:`

A function is a block of code. In a function, we can use many sequences of code, and we can call the function anywhere.

Without using functions, if you write any code, it will take more time and memory. If you want to take the result of the same code without a function, you should write every time, but the function will help to reduce this.

Below, you can see the usefulness of functions and how they will help you write perfect code.

### `Example :`

```python
### THIS IS WITHOUT FUNCTION (1st part) ###
a = 3
b = 5
result = a + b
print(result)  # This will print 8


### THIS IS WITH FUNCTION (2nd part) ###
def add_two_numbers(a, b):
    result = a + b
    return result
sum_result = add_two_numbers(3, 5)
print(sum_result)  # This will print 8
```

There are two parts: one is `without function`, and the other is `with function`.

The `1st part` is right, but if we take the result of this, we should write it every time.

But the `2nd part` can help us reduce the time, and we can call this anywhere for a result.

# `2. Reduce unnecessary operations:`

Many times we use unnecessary operations that may make code lengthy.

### `Example - 1:`

```python
### Inefficient Approach ###
a = a + b
a = a - c

### Efficient Approach ###
# Merging in the same line
a = a + (b - c)
```

To perform addition and subtraction simultaneously we can merge them into a single operation.

### `Example - 2:`

### `Inefficient Approach:`

```python
total = 0

for num in range(1, 11):
    if num % 2 == 0:  # Check if the number is even
        total += num
print(total)
```

* We start with an empty variable called `total` to keep track of the sum.
    
* We use a loop to go through each number from `1 to 10`.
    
* For each number, we check if it's even by using the `% (modulo)` operator. The `% 2` operation checks if there is a remainder when dividing the number by 2. If there's no remainder, it's even.
    
* If the number is even, we add it to the `total`.
    

This approach performs unnecessary operations.

### `Efficient Approach:`

```python
total = 0

for num in range(2, 11, 2):
    total += num
print(total)
```

* We still start with an empty variable called `total` to keep track of the sum.
    
* We use a loop to go through each even number from `2 to 10`.
    
* We start the loop at 2 (the first even number) and increment by 2 in each step.
    
* For each iteration, we directly add the current even number to the `total` without checking if it's even or not.
    

In simple terms, the efficient approach doesn't waste time checking if numbers are even because it already knows they are. It directly adds the even numbers to the total, making the code simpler and faster.

# `3. Avoiding Global Variables:`

Using global variables can make code harder to work with. It's better to use local variables or function parameters for cleaner and more maintainable code.

### `Inefficient Approach (Using Global Variables):`

```python
length = 5
width = 3

def calculate_rectangle_area():
    area = length * width
    return area

result = calculate_rectangle_area()
print(f"The area of the rectangle is: {result}")
```

In this code, `length` and `width` is defined as global variables outside the function. The function `calculate_rectangle_area` uses these global variables to calculate the area of the rectangle.

### `Efficient Approach (Avoiding Global Variables):`

```python
def calculate_rectangle_area(length, width):
    area = length * width
    return area

length = 5
width = 3

result = calculate_rectangle_area(length, width)
print(f"The area of the rectangle is: {result}")
```

In this code, we pass `length` and `width` as parameters for the `calculate_rectangle_area` function, eliminating the need for global variables.

This way, the function doesn't need `global variables`. It works on its own using the given values to figure out the area. The function is self-contained and relies on the provided parameters to calculate the area.

It also promotes code reusability, as you can calculate the area for different rectangles by providing different values.

# `4. Profile Your Code:`

Profiling helps you identify performance bottlenecks in your code. Python's built-in `cProfile` module can help you pinpoint which parts of your code need optimization.

### `Inefficient Approach (Manual Timing):`

```python
import time

# Function to be profiled
def slow_function():
    for _ in range(1000000):
        result = 2 * 2

start_time = time.time()

# Call the slow function
slow_function()

end_time = time.time()

execution_time = end_time - start_time
print(f"Execution time: {execution_time} seconds")
```

In this inefficient approach, we manually record the start and end times to measure the execution time of the `slow_function`.

### `Efficient Approach (Using cProfile):`

```python
import cProfile

# Function to be profiled
def slow_function():
    for i in range(1000000):
        result = 2 * 2

if __name__ == "__main__":
    cProfile.run("slow_function()")
```

In this efficient approach, we use the `cProfile` module to profile the `slow_function`. It automatically records function calls, execution times, and other profiling information, providing more detailed and accurate insights into the code's performance.

Using `cProfile` is an efficient way to profile code because it automates the process and gives you a comprehensive view of your code's performance characteristics.

# `5. Reduce your use of If-Else:`

If-else conditions are best to work with but the user needs to reduce the use of them or if using then use them properly and try to put the condition which has a high probability of matching first.

### `Inefficient Approach (With Many If-Else Statements):`

```python
product_category = "Electronics"
price = 0

if product_category == "Electronics":
    price = 500
elif product_category == "Clothing":
    price = 50
elif product_category == "Books":
    price = 10
elif product_category == "Toys":
    price = 25
elif product_category == "Furniture":
    price = 1000
else:
    price = 0  # Default price for unknown categories

print(f"The price of the product is: ${price}")
```

In this inefficient approach, we have multiple `if-else` statements to check the product category and set the price accordingly. This approach can become less maintainable as the number of categories grows.

### `Efficient Approach (Using a Dictionary):`

```python
product_category = "Electronics"

category_prices = {
    "Electronics": 500,
    "Clothing": 50,
    "Books": 10,
    "Toys": 25,
    "Furniture": 1000
}

price = category_prices.get(product_category, 0)

print(f"The price of the product is: ${price}")
```

* `product_category` represents the category of the product you want to determine the price for.
    
* `category_prices` is a dictionary that maps product categories to their respective prices.
    
* `price` is calculated by using the `.get()` method of the dictionary, which retrieves the price based on the `product_category`. If the category is not found in the dictionary, it defaults to a price of 0.
    
* The final line prints the calculated price, indicating the price of the product based on its category.