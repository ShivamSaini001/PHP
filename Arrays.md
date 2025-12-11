# 📌 What is an Array in PHP?

An **array** in PHP is a **special variable** that can store **multiple values** using a single variable name.

PHP arrays are very powerful because they can store **different data types** together (strings, numbers, booleans, objects, even other arrays).


## ✔️ Why Do We Use Arrays?
- To store **multiple values** in one variable.
- To group related data together.
- To perform operations like sorting, searching, looping.
- Makes code clean and easy to manage.

---
## 🧱 Types of Arrays in PHP
PHP supports **3 main types** of arrays:

### 1️⃣ Indexed Array (Numeric Array)
- Indexed arrays use numeric indexes starting from **0**. 
- These arrays are ideal when you need to store a list of items where the order matters.

#### 🔹 Example
```php
<?php
    $colors = ["Red", "Green", "Blue"];
    echo $colors[0]; // Output: Red
?>
```

---

### 2️⃣ Associative Array
- An **Associative Array** in PHP is an array where **each value is stored with a custom key (string key)** instead of a numeric index.
- Stores data in **key** → **value** pairs.
- Helps in storing structured data (like student info, product info).
- Makes code easy to read and understand.
- Keys must be unique.
  
#### 🔹 Example
```php
<?php
    $student = [
        "name" => "Shivam",
        "age" => 22,
        "city" => "Delhi"
    ];
    echo $student["name"]; // Output: Shivam
?>
```

#### Looping Through Associative Array
```php
<?php
    foreach ($student as $key => $value) {
        echo $key . ": " . $value . "<br>";
    }
?>
```
---

### 3️⃣ Multidimensional Array
- Multidimensional arrays are arrays that contain other arrays as elements. 
- These are used to represent more complex data structures, such as matrices, records or tables data.
  
#### 🔹 Example 1
```php
<?php
    $students = [
        ["Shivam", 22, "BCA"],
        ["Rahul", 21, "B.Tech"],
        ["Amit", 23, "MCA"]
    ];

    echo $students[0][0]; // Output: Shivam
?>
```

#### 🔹 Example 2
```php
<?php
    $students = [
        [
            "name" => "Shivam",
            "age" => 22,
            "course" => "BCA"
        ],
        [
            "name" => "Rahul",
            "age" => 21,
            "course" => "B.Tech"
        ]
    ];

    echo $students[1]["name"];  // Output: Rahul
?>
```

#### Looping Through Multidimensional Array
```php
<?php
    foreach ($students as $student) {
        foreach ($student as $key => $value) {
            echo $key . ": " . $value . "<br>";
        }
        echo "<hr>";
    }
?>
```

---

## 📌 Creating Array Using `array()` Function in PHP

**array()** is a function used to create any type of array in PHP.
This is the **older but still valid** method of creating arrays before PHP introduced the short `[]` syntax.

### 1️⃣ Creating an Indexed Array Using array()

#### 🔹 Example
```php
<?php
    $colors = array("Red", "Green", "Blue");
    echo $colors[0];   // Output: Red
?>
```

### 2️⃣ Creating an Associative Array Using array()

#### 🔹 Example
```php
<?php
    $student = array(
        "name" => "Shivam",
        "age"  => 22,
        "city" => "Delhi"
    );

    echo $student["city"]; // Output: Delhi
?>
```

### 3️⃣ Creating a Multidimensional Array Using array()

#### 🔹 Example
```php
<?php
    $students = array(
        array("Shivam", 22, "BCA"),
        array("Rahul", 21, "B.Tech"),
        array("Amit", 23, "MCA")
    );

    echo $students[0][0]; // Output: Shivam
?>
```
---

## 📌 Array Methods (Array Functions) in PHP

PHP provides many built-in **array functions** to work with arrays easily.  
These functions help in adding, removing, sorting, searching, merging, splitting, and modifying arrays.  
Below are the **most important array methods** you must know for exams, interviews, and real coding.


### 1️⃣ Adding Elements to an Array

> ### ✔️ array_push() — 
> Adds one or more elements **to the end** of an array.
>
> #### Example:
> ```php
> <?php
>     $colors = ["Red", "Green"];
>     array_push($colors, "Blue", "Yellow"); // ["Red", "Green", "Blue", "Yellow"]
> ?>
> ```
> 
> ### ✔️ array_unshift() —
> Adds one or more elements at the start of an array.
> 
> #### Example:
> ```php
> <?php
>    $colors = ["Red", "Green"];
>    array_unshift($colors, "Black"); // ["Black", "Red", "Green"]
> ?>
> ```
> 

### 2️⃣ Removing Elements from an Array

> ### ✔️ array_pop() —
> Removes and returns the last element.
> 
> #### Example:
> ```php
> <?php
>   $colors = ["Red", "Green", "Blue"];
>   $removed = array_pop($colors);  // ["Red", "Green"]
>   echo $removed;  // Blue
> ?>
> ```
>
> ### ✔️ array_shift() —
> Removes and returns the first element.
> 
> #### Example:
> ```php
> <?php
>   $colors = ["Red", "Green", "Blue"];
>   $removed = array_shift($colors); // ["Green", "Blue"]
>   echo $removed;  // Red
> ?>
> ```

### 3️⃣ Searching in Arrays

> ### ✔️ in_array() —
> Returns **true** if a value exists otherwise return **false**.
> 
> #### Example:
> ```php
> <?php
>   $colors = ["Red", "Green", "Blue"];
>   $removed = array_pop($colors);  // ["Red", "Green"]
>   echo $removed;  // Blue
> ?>
> ```
>