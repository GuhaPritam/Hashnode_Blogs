---
title: "Operations on list in python"
seoTitle: "Operations on list in python"
seoDescription: "A list is a variable type that can store multiple items. This is mutable, which means we can make changes to the list after creating it."
datePublished: Wed May 01 2024 09:08:06 GMT+0000 (Coordinated Universal Time)
cuid: clvnlh12a000008l1fcungnwu
slug: operations-on-list-in-python
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1714382374980/46c66715-46bb-4d90-a447-05bb28ae0ea0.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1714554146354/99103d72-c655-4254-acf0-513aa1b8d7a3.png
tags: software-development, python, fundamentals, python3, coding, list, python-projects

---

A list is a `variable` type that can store `multiple items`. This is `mutable`, which means we can make changes to the list after creating it. This is also a type of Data Type.

## `Types of Lists:`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714400670157/18a6c4be-4535-440e-9a9d-13c1b5014c80.png align="center")

## `Interception List Items:`

### `Example - 1 :`

* It replaces the element at index 1 ("mother") with "daughter" using the assignment `obj[1] = "daughter"`.
    
    ```python
    obj = ["father", "mother", "son"]
    obj[1] = "daughter"
    print(obj)
    ```
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714404612933/1690073b-4a34-4142-8a46-14759dcca04f.png align="center")

### `Example - 2 :`

* It will modify the main array by adding the second and third index that I provided.
    
    ```python
    obj = ["father", "mother", "son"]
    obj[1:2] = ["😂", "😊"]
    print(obj)
    ```
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714405640018/e01cc26d-bf50-45be-aba6-bf4b7731d50b.png align="center")

### `Example - 3 :`

* Accessing a list within a list means that the second list is inside the main list. To reach the second list, you first access the main variable and then navigate step by step to go deeper.
    
    ```python
    mixed_list = [1, "apple", 3.14, True, [5, 6, 7]]
    print(mixed_list)
    print(mixed_list[2])
    print(mixed_list[4][1])
    ```
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714406093130/d8cf36f9-d48e-46e3-a3cd-992b605ba742.png align="center")

## `Examples of List Methods:`

### `1. append ()`

* This file method adds a single element to the `end of the list`. We cannot directly append multiple elements in a single `append()` call.
    
    ```python
    obj = ["😂", "🤪", "😀"]
    obj.append('👺')
    print('\nAppend String --', obj)
    
    obj = ["😂", "🤪", "😀"]
    obj.append(True)
    print('\nAppend Boolean --', obj)
    
    obj = ["😂", "🤪", "😀"]
    obj.append(4)
    print('\nAppend Number --', obj)
    
    obj = ["😂", "🤪", "😀"]
    obj.append([4, 5])
    print('\nAppend 2 elements in one list will convert a single emement  --', obj)
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714541458630/2a2eb989-5deb-4b67-840d-bba1c4cf0ff3.png align="left")
    

### `2. extend ()`

* The `extend()` method adds the given list elements to the end of the current list. When you use `extend()` with a string, each letter of the string is added to the list as a separate element.
    
    ```python
    obj = ["😂", "🤪", "😀"]
    obj.extend('👺Pritam')
    print('\nAppend String --', obj)
    
    obj = ["😂", "🤪", "😀"]
    obj.extend([True])
    print('\nAppend Boolean --', obj)
    
    obj = [12, 22, 33]
    obj.extend([1, 2, 3])
    print('\nAppend List --', obj)
    
    obj = ['👺', '😡', '🥵']
    obj.extend(('❄', '🌤️', '🌧️'))
    print('\nAppend Tuple --', obj)
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714541846938/109f3cf0-def8-4b0b-84c8-dcc5613d3cad.png align="left")
    

### `3. insert ()`

* To add an item to a specific position in a list, you can use the `insert()` method. This method requires two arguments: one for the position where you want to add and one for the element.
    
    ```python
    obj = ["😂", "🤪", "😀"]
    obj.insert(1, '👺pritam')
    print('\nInsert emoji --', obj)
    
    obj = ["😂", "🤪", "😀"]
    obj.insert(1, True)
    print('\nInsert Boolean --', obj)
    
    obj = [1, 2, 3]
    obj.insert(1, 4)
    print('\nInsert Number --', obj)
    
    obj = ["😂", "🤪", "😀"]
    obj.insert(1, [4, 3])
    print('\nInsert Number --', obj)
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714543965314/4af6dd1c-992a-442a-ba41-ae1f55af8fd5.png align="left")
    

### `4. pop ()`

* The `pop()` method removes the specified index. If you don't mention the index, it removes the `last` item.
    
    ```python
    obj = ["First", "Second", "Third"]
    obj.pop(2)
    print('\nRemove Last 2nd element --', obj)
    
    obj = [1, 2, 3]
    obj.pop()
    print('\nRemove last Item --', obj)
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714545239811/a3035346-9520-4e91-9311-127bc330185c.png align="left")
    

### `5. remove ()`

* The `remove()` method deletes the item we specify. We need to provide the exact item we want to remove.
    
    ```python
    obj = ["First", "Second", "Third"]
    obj.remove("Second")
    print('\nRemove Last 2nd element --', obj)
    
    obj = [1, 2, 3]
    obj.remove(3)
    print('\nRemove last Item --', obj)
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714547439041/2276651d-7eed-48df-a3d8-d29d480a37a4.png align="left")
    

### `6. clear () & del`

* The `clear()` remove all elements from the lists. The list is still there, but it has no items in it. The `del` keyword can delete the list entirely.
    
    ```python
    obj = ["First", "Second", "Third"]
    obj.clear()
    print('\nRemove all the elements --', obj)
    
    obj = [1, 2, 3]
    obj.clear()
    print('\nRemove all the elements --', obj)
    
    del obj
    print('\nRemove the list  --')
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714550713542/73eaf834-a8f2-43dd-9fe8-ce44a14be8e1.png align="left")
    

### `7. sort ()`

* List objects have a `sort()` method that will sort the list alphabetically or numerically, by default, in an ascending order.
    
    ```python
    obj = ["C", "B", "A"]
    obj.sort()
    print('\nSort alphabetically --', obj)
    
    obj = ["C", "B", "a"]
    obj.sort()
    print('\nAscending Order by default --', obj)
    
    obj = ["C", "B", "a"]
    obj.sort(reverse=True)
    print('\nAscending Order by Manually --', obj)
    
    obj = [100, 2, 3]
    obj.sort()
    print('\nSort by Numerically --', obj)
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714552541031/48016cdf-d935-4edb-814f-bd903d20b031.png align="left")
    

### `8. copy () & list()`

* There are ways to duplicate a list. One method is to use the built-in List method `copy()`. Another way is to use the built-in method `list()`.
    
    ```python
    obj = ["First", "Second", "Third"]
    my_list = obj.copy()
    print('\nCopy main list --', my_list)
    
    obj = [1, 2, 3]
    my_list = list(obj)
    print('\nRemove all the elements --', obj)
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714553544005/61487e07-83f6-4de2-9172-1045e349fd8f.png align="left")
    

%[https://github.com/GuhaPritam] 

%[https://www.pritamguha.com/]