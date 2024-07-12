---
title: "What is Function Scope?"
seoTitle: "What is Function Scope?"
seoDescription: "Function scope defines variable accessibility within a specific function, restricting their use to that code block."
datePublished: Wed Aug 02 2023 09:57:39 GMT+0000 (Coordinated Universal Time)
cuid: clktk16nz000709mfbap14y37
slug: what-is-function-scope
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1689658481244/f4cc4a5b-df49-48b4-97c9-ef275469696a.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1689929720551/b11a4ef1-d1a9-4557-983d-1586143db898.png
tags: software-development, python, developer, coding, beginners, global

---

### `What is the meaning of function scope?`

This scope means that the variables are only accessible in the function in which they are declared. In one file, there are many types of functions. In those functions, there are many variables. But those variables we can't use everywhere because every variable should be in one area. All of the area's call scope.

### `How many scopes are there?`

1. Global Scope.
    
2. Local Scope.
    
3. Block Scope (Conditional Scope).
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689685276745/a0196b46-c782-4135-920d-6862a68d4bfe.png align="center")

### `Explaining all the scope by code:`

### `Global Scope:`

* For this scope variable is declared `outside a function`.
    
* The Global Variable can be accessed from `anywhere in a program`.
    
* Variables declared with `var, let and const`.
    

```basic
  global_var = 10  # Variable in the global scope
  
  def my_function():
      print(global_var)  # The global variable inside a function
  
  my_function()
  print(global_var)  # The global variable outside the function
```

### `Local Scope:`

* For this scope variable is declared `inside a function`.
    
* The Local Variable can be accessed only `inside the function`.
    
* Variables declared with `var, let and const`.
    
* Once the function is finished, the local variables are destroyed.
    

```basic
  def my_function():
      local_var = 20  # Variable in the local scope
      print(local_var)
  
  my_function()
  # print(local_var)  error will come
```

### `Block Scope (Conditional Scope):`

* They are only accessible within the `IF` block and are not accessible outside of it.
    
* Variables declared with `let and const`.
    

```basic
if (true) {
    var block_var = 30;  // Variable with block scope 
    console.log(block_var);
}

console.log(block_var);  // This will work in JavaScript since var has function scope
```

%[https://youtube.com/@codeplayer-3828?si=HoSahYy9Q8t6Jfrt] 

%[https://www.pritamguha.com/] 

%[https://github.com/GuhaPritam]