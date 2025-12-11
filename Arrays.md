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

### ✔️ array_push() — 
Adds one or more elements **to the end** of an array.
>
#### Example:
```php
<?php
    $colors = ["Red", "Green"];
    array_push($colors, "Blue", "Yellow"); // ["Red", "Green", "Blue", "Yellow"]
?>
```

### ✔️ array_unshift() —
Adds one or more elements at the start of an array.

#### Example:
```php
<?php
   $colors = ["Red", "Green"];
   array_unshift($colors, "Black"); // ["Black", "Red", "Green"]
?>
```


### 2️⃣ Removing Elements from an Array

### ✔️ array_pop() —
Removes and returns the last element.

#### Example:
```php
<?php
  $colors = ["Red", "Green", "Blue"];
  $removed = array_pop($colors);  // ["Red", "Green"]
  echo $removed;  // Blue
?>
```
>
### ✔️ array_shift() —
Removes and returns the first element.

#### Example:
```php
<?php
    $colors = ["Red", "Green", "Blue"];
    $removed = array_shift($colors); // ["Green", "Blue"]
    echo $removed;  // Red
?>
```

### 3️⃣ Searching in Arrays

### ✔️ in_array() —
Returns **true** if a value exists otherwise return **false**.

#### Example:
```php
<?php
    $colors = ["Red", "Green", "Blue"];
    in_array("Green", $colors); // true
?>
```

### ✔️ array_search() —
Returns the **key** if value is found, otherwise **false**.

#### Example:
```php
<?php
    $array_search("Blue", ["Red", "Blue", "Green"]); // 1
?>
```

### 4️⃣ Counting Elements

### ✔️ count() —
Returns the **number of items** in an array.

#### Example:
```php
<?php
    count(["A", "B", "C"]); // 3
?>
```

### ✔️ sizeof() —
Same as count().


# PHP Array Functions — Full Detailed Table 

<table>
  <thead>
    <tr>
      <th>Function Name</th>
      <th>Syntax</th>
      <th>Description + Example + Output</th>
    </tr>
  </thead>
  <tbody>
    <tr>
        <th colspan="3">Creating / Initializing Arrays</th>
    </tr>
    <tr>
      <td>array()</td>
      <td><code>array(v1, v2, ...)</code></td>
      <td>Creates an indexed, associative, or multidimensional array. Example: <code>$colors = array("Red","Blue");</code><br>Output: <code>["Red","Blue"]</code></td>
    </tr>
    <tr>
      <td>array_fill()</td>
      <td><code>array_fill(start_index, count, value)</code></td>
      <td>Fills an array with <code>count</code> copies of <code>value</code> starting at <code>start_index</code>. Example: <code>array_fill(0,3,"x");</code><br>Output: <code>["x","x","x"]</code></td>
    </tr>
    <tr>
      <td>array_fill_keys()</td>
      <td><code>array_fill_keys(keys_array, value)</code></td>
      <td>Creates an associative array using <code>keys_array</code> for keys and sets each to <code>value</code>. Example: <code>array_fill_keys(["a","b"],0);</code><br>Output: <code>["a"=>0,"b"=>0]</code></td>
    </tr>
    <tr>
      <td>range()</td>
      <td><code>range(start, end, step)</code></td>
      <td>Generates an array of numbers/characters from start to end with optional step. Example: <code>range(1,5);</code><br>Output: <code>[1,2,3,4,5]</code></td>
    </tr>
    <tr>
        <th colspan="3">Adding / Inserting Elements</th>
    </tr>
    <tr>
      <td>array_push()</td>
      <td><code>array_push($arr, v1, v2...)</code></td>
      <td>Adds one or more elements to the end of an array. Example: <code>$a=["Red","Green"]; array_push($a,"Blue");</code><br>Output: <code>["Red","Green","Blue"]</code></td>
    </tr>
    <tr>
      <td>array_unshift()</td>
      <td><code>array_unshift($arr, v1, v2...)</code></td>
      <td>Adds one or more elements to the beginning of an array. Example: <code>$a=["Red","Green"]; array_unshift($a,"Black");</code><br>Output: <code>["Black","Red","Green"]</code></td>
    </tr>
    <tr>
      <td>array_splice()</td>
      <td><code>array_splice($arr, offset, length, replacement?)</code></td>
      <td>Removes elements from <code>$arr</code> and optionally replaces them. Modifies original array. Example: <code>$a=["A","B","C","D"]; array_splice($a,1,2,["X"]);</code><br>Output (modified $a): <code>["A","X","D"]</code></td>
    </tr>
    <tr>
        <th colspan="3">Removing / Popping Elements</th>
    </tr>
    <tr>
      <td>array_pop()</td>
      <td><code>array_pop($arr)</code></td>
      <td>Removes and returns the last element. Example: <code>$a=["A","B","C"]; $v=array_pop($a);</code><br><strong>$v:</strong> <code>"C"</code> <strong>$a:</strong> <code>["A","B"]</code></td>
    </tr>
    <tr>
      <td>array_shift()</td>
      <td><code>array_shift($arr)</code></td>
      <td>Removes and returns the first element. Example: <code>$a=["A","B","C"]; $v=array_shift($a);</code><br><strong>$v:</strong> <code>"A"</code> <strong>$a:</strong> <code>["B","C"]</code></td>
    </tr>
    <tr>
      <td>unset()</td>
      <td><code>unset($arr[$key])</code></td>
      <td>Removes the element with specified key from array. Example: <code>$a=["a"=>1,"b"=>2]; unset($a["a"]);</code><br>Output: <code>["b"=>2]</code></td>
    </tr>
    <tr>
        <th colspan="3">Searching / Checking Existence</th>
    </tr>
    <tr>
      <td>in_array()</td>
      <td><code>in_array(value, $arr, strict=false)</code></td>
      <td>Checks if a value exists in array. <code>strict</code> enforces type comparison. Example: <code>in_array("2",[1,"2"]);</code> → <code>true</code>; <code>in_array(2,[1,"2"], true);</code> → <code>false</code></td>
    </tr>
    <tr>
      <td>array_search()</td>
      <td><code>array_search(value, $arr, strict=false)</code></td>
      <td>Returns the key/index of the first matching value or <code>false</code> if not found. Example: <code>array_search("Blue",["Red","Blue"]);</code><br>Output: <code>1</code></td>
    </tr>
    <tr>
      <td>array_key_exists()</td>
      <td><code>array_key_exists(key, $arr)</code></td>
      <td>Checks if a key exists in an array (returns true even if value is <code>null</code>). Example: <code>array_key_exists("name",["name"=>null]);</code><br>Output: <code>true</code></td>
    </tr>
    <tr>
      <td>isset()</td>
      <td><code>isset($arr[$key])</code></td>
      <td>Checks if key exists AND value is not <code>null</code>. Example: <code>isset(["a"=>null]["a"]);</code><br>Output: <code>false</code></td>
    </tr>
    <tr>
        <th colspan="3">Counting / Size</th>
    </tr>
    <tr>
      <td>count()</td>
      <td><code>count($arr)</code></td>
      <td>Returns number of elements. Example: <code>count([1,2,3]);</code><br>Output: <code>3</code></td>
    </tr>
    <tr>
      <td>sizeof()</td>
      <td><code>sizeof($arr)</code></td>
      <td>Alias of <code>count()</code>. Example: <code>sizeof([1,2]);</code><br>Output: <code>2</code></td>
    </tr>
    <tr>
      <td>array_count_values()</td>
      <td><code>array_count_values($arr)</code></td>
      <td>Counts frequency of each value and returns associative array. Example: <code>array_count_values([1,2,2,3]);</code><br>Output: <code>[1=>1,2=>2,3=>1]</code></td>
    </tr>
    <tr>
        <th colspan="3">Sorting (Indexed &amp; Associative)</th>
    </tr>
    <tr>
      <td>sort()</td>
      <td><code>sort(&$arr, flags?)</code></td>
      <td>Sorts indexed array by value ascending, reindexes numeric keys. Example: <code>$n=[3,1,2]; sort($n);</code><br>Output: <code>[1,2,3]</code></td>
    </tr>
    <tr>
      <td>rsort()</td>
      <td><code>rsort(&$arr, flags?)</code></td>
      <td>Sorts indexed array by value descending. Example: <code>rsort([1,3,2]);</code><br>Output: <code>[3,2,1]</code></td>
    </tr>
    <tr>
      <td>asort()</td>
      <td><code>asort(&$arr, flags?)</code></td>
      <td>Sorts associative array by value (ascending) and preserves keys. Example: <code>asort(["A"=>50,"B"=>30]);</code><br>Output: <code>["B"=>30,"A"=>50]</code></td>
    </tr>
    <tr>
      <td>arsort()</td>
      <td><code>arsort(&$arr, flags?)</code></td>
      <td>Sorts associative array by value (descending). Example: <code>arsort(["A"=>50,"B"=>30]);</code><br>Output: <code>["A"=>50,"B"=>30]</code></td>
    </tr>
    <tr>
      <td>ksort()</td>
      <td><code>ksort(&$arr, flags?)</code></td>
      <td>Sorts associative array by key (ascending). Example: <code>ksort(["b"=>2,"a"=>1]);</code><br>Output: <code>["a"=>1,"b"=>2]</code></td>
    </tr>
    <tr>
      <td>krsort()</td>
      <td><code>krsort(&$arr, flags?)</code></td>
      <td>Sorts associative array by key (descending). Example: <code>krsort(["b"=>2,"a"=>1]);</code><br>Output: <code>["b"=>2,"a"=>1]</code></td>
    </tr>
    <tr>
      <td>natsort()</td>
      <td><code>natsort(&$arr)</code></td>
      <td>Natural order sorting (human-friendly). Example: <code>natsort(["img1","img12","img2"]);</code><br>Output (keys preserved): <code>["img1","img2","img12"]</code></td>
    </tr>
    <tr>
      <td>natcasesort()</td>
      <td><code>natcasesort(&$arr)</code></td>
      <td>Natural order sort case-insensitive.</td>
    </tr>
    <tr>
      <td>usort()</td>
      <td><code>usort(&$arr, callback)</code></td>
      <td>Sorts array using user-defined comparison function (reindexes). Example: <code>usort($a, fn($x,$y)=>$x-$y);</code></td>
    </tr>
    <tr>
      <td>uasort()</td>
      <td><code>uasort(&$arr, callback)</code></td>
      <td>Sorts associative array using user function and preserves keys.</td>
    </tr>
    <tr>
      <td>uksort()</td>
      <td><code>uksort(&$arr, callback)</code></td>
      <td>Sorts associative array by keys using user function.</td>
    </tr>
    <tr>
      <td>array_multisort()</td>
      <td><code>array_multisort(&$arr1, sort_flags1, &$arr2, ...)</code></td>
      <td>Sorts multiple arrays or multi-dimensional array by columns. Example: <code>array_multisort($scores, SORT_DESC, $names);</code></td>
    </tr>
    <tr>
        <th colspan="3">Filtering / Mapping / Reducing</th>
    </tr>
    <tr>
      <td>array_filter()</td>
      <td><code>array_filter($arr, callback, flag=0)</code></td>
      <td>Filters elements using callback — keeps elements where callback returns truthy. Example: <code>array_filter([5,10,20], fn($n)=>$n>10);</code><br>Output: <code>[2=>20]</code> (original keys preserved)</td>
    </tr>
    <tr>
      <td>array_map()</td>
      <td><code>array_map(callback, $arr1, $arr2...)</code></td>
      <td>Applies callback to each element and returns new array. Example: <code>array_map(fn($n)=>$n*2,[1,2]);</code><br>Output: <code>[2,4]</code></td>
    </tr>
    <tr>
      <td>array_reduce()</td>
      <td><code>array_reduce($arr, callback, initial)</code></td>
      <td>Iteratively reduces array to single value using callback. Example: <code>array_reduce([1,2,3], fn($carry,$n)=>$carry+$n,0);</code><br>Output: <code>6</code></td>
    </tr>
    <tr>
      <td>array_walk()</td>
      <td><code>array_walk(&$arr, callback, userdata?)</code></td>
      <td>Applies callback to each element — intended for side-effects; can modify array values. Example: <code>array_walk($a, fn(&$v,$k)=>$v*=2);</code></td>
    </tr>
    <tr>
      <td>array_walk_recursive()</td>
      <td><code>array_walk_recursive(&$arr, callback)</code></td>
      <td>Like array_walk but recursive for nested arrays.</td>
    </tr>
    <tr>
        <th colspan="3">Combining / Merging / Replacing Arrays</th>
</tr>
    <tr>
      <td>array_merge()</td>
      <td><code>array_merge($a1, $a2, ...)</code></td>
      <td>Merges arrays — for numeric keys reindexes; for string keys later values override. Example: <code>array_merge([1,2],[3,4]);</code><br>Output: <code>[1,2,3,4]</code></td>
    </tr>
    <tr>
      <td>array_merge_recursive()</td>
      <td><code>array_merge_recursive($a1, $a2, ...)</code></td>
      <td>Merges arrays recursively — duplicate string keys become arrays of values. Example: <code>array_merge_recursive(["k"=>1], ["k"=>2]);</code><br>Output: <code>["k"=>[1,2]]</code></td>
    </tr>
    <tr>
      <td>array_replace()</td>
      <td><code>array_replace($base, $replacements...)</code></td>
      <td>Replaces values in base array with values from replacements (non-recursive). Example: <code>array_replace(["a"=>1,"b"=>2], ["b"=>3]);</code><br>Output: <code>["a"=>1,"b"=>3]</code></td>
    </tr>
    <tr>
      <td>array_replace_recursive()</td>
      <td><code>array_replace_recursive($base, $repl...)</code></td>
      <td>Like array_replace() but recursive for nested arrays.</td>
    </tr>
    <tr>
        <th colspan="3">Extract / Slice / Subset</th>
    </tr>
    <tr>
      <td>array_slice()</td>
      <td><code>array_slice($arr, offset, length=null, preserve_keys=false)</code></td>
      <td>Returns a slice (does not modify original). Example: <code>array_slice(["R","G","B","Y"],1,2);</code><br>Output: <code>["G","B"]</code></td>
    </tr>
    <tr>
      <td>array_splice()</td>
      <td><code>array_splice(&$arr, offset, length=null, replacement=[])</code></td>
      <td>Removes/replaces portion and modifies original array. Example: <code>$a=["A","B","C"]; array_splice($a,1,1,["X","Y"]);</code><br>Output ($a): <code>["A","X","Y","C"]</code></td>
    </tr>
    <tr>
      <td>array_chunk()</td>
      <td><code>array_chunk($arr, size, preserve_keys=false)</code></td>
      <td>Splits array into chunks of size. Example: <code>array_chunk([1,2,3,4],2);</code><br>Output: <code>[[1,2],[3,4]]</code></td>
    </tr>
    <tr>
        <th colspan="3">Keys / Values / Transformations</th>
    </tr>
    <tr>
      <td>array_keys()</td>
      <td><code>array_keys($arr, search_value=null, strict=false)</code></td>
      <td>Returns all keys or keys for a given value. Example: <code>array_keys(["a"=>1,"b"=>2]);</code><br>Output: <code>["a","b"]</code></td>
    </tr>
    <tr>
      <td>array_values()</td>
      <td><code>array_values($arr)</code></td>
      <td>Returns all values (reindexes numerically). Example: <code>array_values(["a"=>1,"b"=>2]);</code><br>Output: <code>[1,2]</code></td>
    </tr>
    <tr>
      <td>array_flip()</td>
      <td><code>array_flip($arr)</code></td>
      <td>Exchanges keys and values (values must be valid keys). Example: <code>array_flip(["a"=>"x","b"=>"y"]);</code><br>Output: <code>["x"=>"a","y"=>"b"]</code></td>
    </tr>
    <tr>
      <td>array_change_key_case()</td>
      <td><code>array_change_key_case($arr, CASE_LOWER|CASE_UPPER)</code></td>
      <td>Changes case of all keys. Example: <code>array_change_key_case(["A"=>1,"B"=>2], CASE_LOWER);</code><br>Output: <code>["a"=>1,"b"=>2]</code></td>
    </tr>
    <tr>
      <td>array_column()</td>
      <td><code>array_column($arr, column_key, index_key=null)</code></td>
      <td>Returns values from a single column in a multi-dimensional array. Example: <code>array_column([["id"=>1,"name"=>"A"],["id"=>2,"name"=>"B"]],"name");</code><br>Output: <code>["A","B"]</code></td>
    </tr>
    <tr>
      <td>array_key_first()</td>
      <td><code>array_key_first($arr)</code></td>
      <td>Returns the first key of the array (PHP 7.3+). Example: <code>array_key_first(["a"=>1,"b"=>2]);</code><br>Output: <code>"a"</code></td>
    </tr>
    <tr>
      <td>array_key_last()</td>
      <td><code>array_key_last($arr)</code></td>
      <td>Returns the last key of the array (PHP 7.3+). Example: <code>array_key_last(["a"=>1,"b"=>2]);</code><br>Output: <code>"b"</code></td>
    </tr>
    <tr>
      <td>array_is_list()</td>
      <td><code>array_is_list($arr)</code></td>
      <td>Checks if array is a list (consecutive integer keys starting at 0) (PHP 8.1+). Example: <code>array_is_list(["a","b"]);</code><br>Output: <code>true</code></td>
    </tr>
    <tr>
        <th colspan="3">Set / Difference / Intersection</th>
    </tr>
    <tr>
      <td>array_diff()</td>
      <td><code>array_diff($arr1,$arr2,...)</code></td>
      <td>Computes values present in <code>$arr1</code> but not in others. Example: <code>array_diff([1,2,3],[2,4]);</code><br>Output: <code>[0=>1,2=>3]</code></td>
    </tr>
    <tr>
      <td>array_diff_assoc()</td>
      <td><code>array_diff_assoc($a,$b)</code></td>
      <td>Compares keys AND values and returns differences. Example: <code>array_diff_assoc(["a"=>1,"b"=>2],["a"=>1,"b"=>3]);</code><br>Output: <code>["b"=>2]</code></td>
    </tr>
    <tr>
      <td>array_diff_key()</td>
      <td><code>array_diff_key($a,$b)</code></td>
      <td>Compares keys only; returns keys from <code>$a</code> not in <code>$b</code>.</td>
    </tr>
    <tr>
      <td>array_intersect()</td>
      <td><code>array_intersect($a,$b,...)</code></td>
      <td>Returns values present in all arrays. Example: <code>array_intersect([1,2,3],[2,3,4]);</code><br>Output: <code>[1=>2,2=>3]</code></td>
    </tr>
    <tr>
      <td>array_intersect_assoc()</td>
      <td><code>array_intersect_assoc($a,$b)</code></td>
      <td>Compares keys AND values for intersection.</td>
    </tr>
    <tr>
      <td>array_udiff / array_uintersect / ...</td>
      <td><code>array_udiff(...)</code></td>
      <td>Variants that allow user-supplied comparison callbacks for diff/intersect operations.</td>
    </tr>
    <tr>
        <th colspan="3">Random / Shuffle / Utilities</th>
    </tr>
    <tr>
      <td>shuffle()</td>
      <td><code>shuffle(&$arr)</code></td>
      <td>Randomly shuffles elements in-place. Example: <code>$a=[1,2,3]; shuffle($a);</code><br>Output: order randomized, e.g. <code>[2,1,3]</code></td>
    </tr>
    <tr>
      <td>array_rand()</td>
      <td><code>array_rand($arr, num=1)</code></td>
      <td>Returns random key (or array of keys) from <code>$arr</code>. Example: <code>array_rand(["a","b","c"],2);</code><br>Output example: <code>[0,2]</code> (keys)</td>
    </tr>
    <tr>
        <th colspan="3">Mathematical / Aggregate</th>
    </tr>
    <tr>
      <td>array_sum()</td>
      <td><code>array_sum($arr)</code></td>
      <td>Returns sum of values. Example: <code>array_sum([1,2,3]);</code><br>Output: <code>6</code></td>
    </tr>
    <tr>
      <td>array_product()</td>
      <td><code>array_product($arr)</code></td>
      <td>Returns product of values. Example: <code>array_product([2,3,4]);</code><br>Output: <code>24</code></td>
    </tr>
    <tr>
      <td>max() / min()</td>
      <td><code>max($arr) / min($arr)</code></td>
      <td>Return maximum / minimum values from array or arguments. Example: <code>max([1,5,3]);</code> → <code>5</code></td>
    </tr>
    <tr>
        <th colspan="3">Uniqueness / Duplicates</th>
    </tr>
    <tr>
      <td>array_unique()</td>
      <td><code>array_unique($arr, flags?)</code></td>
      <td>Removes duplicate values, preserves first occurrence and keys. Example: <code>array_unique([1,2,2,3]);</code><br>Output: <code>[0=>1,1=>2,3=>3]</code></td>
    </tr>
    <tr>
      <td>array_keys (value search)</td>
      <td><code>array_keys($arr, value, strict=false)</code></td>
      <td>Returns keys that match a specific value (useful for duplicates). Example: <code>array_keys([1,2,2,3],2);</code><br>Output: <code>[1,2]</code></td>
    </tr>
    <tr>
        <th colspan="3">Special / Utility Functions</th>
    </tr>
    <tr>
      <td>compact()</td>
      <td><code>compact(varname1, varname2, ...)</code></td>
      <td>Creates an associative array from variables and their values. Example: <code>$a="x"; $b=2; compact("a","b");</code><br>Output: <code>["a"=>"x","b"=>2]</code></td>
    </tr>
    <tr>
      <td>extract()</td>
      <td><code>extract($assoc_array)</code></td>
      <td>Imports variables from associative array into symbol table (creates variables). Example: <code>extract(["a"=>1]);</code> → now <code>$a == 1</code></td>
    </tr>
    <tr>
      <td>each() <em>(deprecated)</em></td>
      <td><code>each($arr)</code></td>
      <td>Returns current key/value pair and advances pointer. Deprecated in PHP 7.2+. Avoid for modern code.</td>
    </tr>
    <tr>
      <td>list()</td>
      <td><code>list($a,$b)=array(...)</code></td>
      <td>Assigns variables from an array (numeric keys). Example: <code>list($x,$y)=["A","B"];</code> → <code>$x == "A"</code>, <code>$y == "B"</code></td>
    </tr>
  </tbody>
</table>


### ✅ PHP STRING FUNCTIONS — FULL DETAILED TABLE

<table>
  <thead>
    <tr>
      <th>Function Name</th>
      <th>Syntax</th>
      <th>Description + Example + Output</th>
    </tr>
  </thead>
  <tbody>
    <tr><th colspan="3">Creating / Initializing Strings</th></tr>
    <tr>
      <td>Single Quotes</td>
      <td><code>'text'</code></td>
      <td>Single-quoted strings do not parse variables or escape sequences (except \\ and \').<br>
          Example: <code>$s = 'Hello $name';</code><br>
          Output: <code>Hello $name</code></td>
    </tr>
    <tr>
      <td>Double Quotes</td>
      <td><code>"text"</code></td>
      <td>Parses variables and escape sequences.<br>
          Example: <code>$name="Shivam"; echo "Hello $name";</code><br>
          Output: <code>Hello Shivam</code></td>
    </tr>
    <tr>
      <td>Heredoc</td>
      <td><code>&lt;&lt;&lt;TEXT ... TEXT;</code></td>
      <td>Multi-line string with variable parsing.<br>
          Example:<br>
          <code>$name="Shivam";<br>
          $s = &lt;&lt;&lt;X<br>
          Hello $name<br>
          X;<br></code>
          Output: <code>Hello Shivam</code></td>
    </tr>
    <tr>
      <td>Nowdoc</td>
      <td><code>&lt;&lt;&lt;'TEXT' ... TEXT;</code></td>
      <td>Multi-line string without variable parsing.<br>
          Example:<br>
          <code>$s = &lt;&lt;&lt;'X'<br>
          Hello $name<br>
          X;<br></code>
          Output: <code>Hello $name</code></td>
    </tr>
    <!-- Category: String Length / Count -->
    <tr><th colspan="3">Length / Count Functions</th></tr>
    <tr>
      <td>strlen()</td>
      <td><code>strlen($str)</code></td>
      <td>Returns number of characters in string.<br>
          Example: <code>strlen("Hello");</code><br>
          Output: <code>5</code></td>
    </tr>
    <tr>
      <td>str_word_count()</td>
      <td><code>str_word_count($str, format)</code></td>
      <td>Counts words in a string.<br>
          Example: <code>str_word_count("Hello World");</code><br>
          Output: <code>2</code></td>
    </tr>
    <tr>
      <td>substr_count()</td>
      <td><code>substr_count($str, $substring)</code></td>
      <td>Counts how many times a substring appears.<br>
          Example: <code>substr_count("banana","a");</code><br>
          Output: <code>3</code></td>
    </tr>
    <!-- Category: Searching in Strings -->
    <tr><th colspan="3">Searching in Strings</th></tr>
    <tr>
      <td>strpos()</td>
      <td><code>strpos($str, $search)</code></td>
      <td>Finds first occurrence position of substring (case-sensitive).<br>
          Example: <code>strpos("Hello","l");</code><br>
          Output: <code>2</code></td>
    </tr>
    <tr>
      <td>strrpos()</td>
      <td><code>strrpos($str, $search)</code></td>
      <td>Finds last occurrence position of substring.<br>
          Example: <code>strrpos("Hello","l");</code><br>
          Output: <code>3</code></td>
    </tr>
    <tr>
      <td>stripos()</td>
      <td><code>stripos($str, $search)</code></td>
      <td>Case-insensitive version of <code>strpos()</code>.<br>
          Example: <code>stripos("Hello","H");</code><br>
          Output: <code>0</code></td>
    </tr>
    <tr>
      <td>str_contains() (PHP 8+)</td>
      <td><code>str_contains($str, $search)</code></td>
      <td>Returns true if substring exists.<br>
          Example: <code>str_contains("Hello","ell");</code><br>
          Output: <code>true</code></td>
    </tr>
    <tr>
      <td>str_starts_with() (PHP 8+)</td>
      <td><code>str_starts_with($str,$prefix)</code></td>
      <td>Checks if string starts with prefix.<br>
          Example: <code>str_starts_with("Hello","He");</code><br>
          Output: <code>true</code></td>
    </tr>
    <tr>
      <td>str_ends_with() (PHP 8+)</td>
      <td><code>str_ends_with($str,$suffix)</code></td>
      <td>Checks if string ends with suffix.<br>
          Example: <code>str_ends_with("Hello","lo");</code><br>
          Output: <code>true</code></td>
    </tr>
    <!-- Category: Extracting / Substring -->
    <tr><th colspan="3">Extracting / Substring Functions</th></tr>
    <tr>
      <td>substr()</td>
      <td><code>substr($str, start, length)</code></td>
      <td>Returns portion of string.<br>
          Example: <code>substr("Hello",1,3);</code><br>
          Output: <code>ell</code></td>
    </tr>
    <tr>
      <td>strstr()</td>
      <td><code>strstr($str, $search)</code></td>
      <td>Returns part of string from first occurrence.<br>
          Example: <code>strstr("Hello World","World");</code><br>
          Output: <code>World</code></td>
    </tr>
    <tr>
      <td>stristr()</td>
      <td><code>stristr($str, $search)</code></td>
      <td>Case-insensitive version of strstr().<br>
          Example: <code>stristr("Hello","HEL");</code><br>
          Output: <code>Hello</code></td>
    </tr>
    <!-- Category: Replace / Modify -->
    <tr><th colspan="3">Replacing / Modifying Strings</th></tr>
    <tr>
      <td>str_replace()</td>
      <td><code>str_replace(search, replace, str)</code></td>
      <td>Replaces all occurrences of search with replace.<br>
          Example: <code>str_replace("a","x","banana");</code><br>
          Output: <code>bxnxnx</code></td>
    </tr>
    <tr>
      <td>str_ireplace()</td>
      <td><code>str_ireplace(search, replace, str)</code></td>
      <td>Case-insensitive replace.<br>
          Example: <code>str_ireplace("HELLO","Hi","hello");</code><br>
          Output: <code>Hi</code></td>
    </tr>
    <tr>
      <td>substr_replace()</td>
      <td><code>substr_replace(str, replace, start, length)</code></td>
      <td>Replaces a portion of a string.<br>
          Example: <code>substr_replace("Hello","XX",1,3);</code><br>
          Output: <code>HXXo</code></td>
    </tr>
    <!-- Category: Case Conversion -->
    <tr><th colspan="3">Case Conversion</th></tr>
    <tr>
      <td>strtolower()</td>
      <td><code>strtolower($str)</code></td>
      <td>Converts string to lowercase.<br>
          Example: <code>strtolower("HeLLo");</code><br>
          Output: <code>hello</code></td>
    </tr>
    <tr>
      <td>strtoupper()</td>
      <td><code>strtoupper($str)</code></td>
      <td>Converts string to uppercase.<br>
          Example: <code>strtoupper("Hello");</code><br>
          Output: <code>HELLO</code></td>
    </tr>
    <tr>
      <td>ucfirst()</td>
      <td><code>ucfirst($str)</code></td>
      <td>Capitalizes first character.<br>
          Example: <code>ucfirst("hello");</code><br>
          Output: <code>Hello</code></td>
    </tr>
    <tr>
      <td>lcfirst()</td>
      <td><code>lcfirst($str)</code></td>
      <td>Makes first character lowercase.<br>
          Example: <code>lcfirst("Hello");</code><br>
          Output: <code>hello</code></td>
    </tr>
    <tr>
      <td>ucwords()</td>
      <td><code>ucwords($str)</code></td>
      <td>Capitalizes first letter of every word.<br>
          Example: <code>ucwords("hello world");</code><br>
          Output: <code>Hello World</code></td>
    </tr>
    <!-- Category: Trimming -->
    <tr><th colspan="3">Trimming Functions</th></tr>
    <tr>
      <td>trim()</td>
      <td><code>trim($str)</code></td>
      <td>Removes whitespace from both ends.<br>
          Example: <code>trim("  hello  ");</code><br>
          Output: <code>"hello"</code></td>
    </tr>
    <tr>
      <td>ltrim()</td>
      <td><code>ltrim($str)</code></td>
      <td>Removes whitespace from left side.<br>
          Example: <code>ltrim("  hello");</code><br>
          Output: <code>"hello"</code></td>
    </tr>
    <tr>
      <td>rtrim()</td>
      <td><code>rtrim($str)</code></td>
      <td>Removes whitespace from right side.<br>
          Example: <code>rtrim("hello  ");</code><br>
          Output: <code>"hello"</code></td>
    </tr>
    <!-- Category: Splitting and Joining -->
    <tr><th colspan="3">Splitting / Joining Strings</th></tr>
    <tr>
      <td>explode()</td>
      <td><code>explode(delimiter, string)</code></td>
      <td>Splits string into array.<br>
          Example: <code>explode(" ","Hello World");</code><br>
          Output: <code>["Hello","World"]</code></td>
    </tr>
    <tr>
      <td>implode()</td>
      <td><code>implode(separator, array)</code></td>
      <td>Joins array elements into string.<br>
          Example: <code>implode("-",["Hello","World"]);</code><br>
          Output: <code>Hello-World</code></td>
    </tr>
    <!-- Category: Encoding / Decoding -->
    <tr><th colspan="3">Encoding / Decoding</th></tr>
    <tr>
      <td>htmlspecialchars()</td>
      <td><code>htmlspecialchars($str)</code></td>
      <td>Converts HTML special chars to entities.<br>
          Example: <code>htmlspecialchars("&lt;tag&gt;");</code><br>
          Output: <code>&amp;lt;tag&amp;gt;</code></td>
    </tr>
    <tr>
      <td>html_entity_decode()</td>
      <td><code>html_entity_decode($str)</code></td>
      <td>Converts HTML entities back to characters.<br>
          Example: <code>html_entity_decode("&amp;amp;");</code><br>
          Output: <code>&amp;</code></td>
    </tr>
    <tr>
      <td>urlencode()</td>
      <td><code>urlencode($str)</code></td>
      <td>Encodes string for URL.<br>
          Example: <code>urlencode("Hello World");</code><br>
          Output: <code>Hello+World</code></td>
    </tr>
    <tr>
      <td>urldecode()</td>
      <td><code>urldecode($str)</code></td>
      <td>Decodes URL-encoded string.<br>
          Example: <code>urldecode("Hello%20World");</code><br>
          Output: <code>Hello World</code></td>
    </tr>
    <!-- Category: Formatting -->
    <tr><th colspan="3">String Formatting</th></tr>
    <tr>
      <td>printf()</td>
      <td><code>printf(format, args...)</code></td>
      <td>Outputs formatted string.<br>
          Example: <code>printf("Name: %s", "Shivam");</code><br>
          Output: <code>Name: Shivam</code></td>
    </tr>
    <tr>
      <td>sprintf()</td>
      <td><code>sprintf(format, args...)</code></td>
      <td>Returns formatted string.<br>
          Example: <code>$s = sprintf("%d + %d = %d", 2,3,5);</code><br>
          Output: <code>2 + 3 = 5</code></td>
    </tr>
  </tbody>
</table>


### Math functions

<table>
  <thead>
    <tr>
      <th>Function Name</th>
      <th>Syntax</th>
      <th>Description + Example + Output</th>
    </tr>
  </thead>
  <tbody>
    <tr><th colspan="3">Basic / Rounding / Absolute</th></tr>
    <tr>
      <td>abs()</td>
      <td><code>abs(number)</code></td>
      <td>Returns absolute (non-negative) value of number.<br>
      Example:<br><code>abs(-5);</code><br>Output: <code>5</code></td>
    </tr>
    <tr>
      <td>ceil()</td>
      <td><code>ceil(number)</code></td>
      <td>Rounds number **up** to the nearest integer.<br>
      Example:<br><code>ceil(4.2);</code><br>Output: <code>5</code></td>
    </tr>
    <tr>
      <td>floor()</td>
      <td><code>floor(number)</code></td>
      <td>Rounds number **down** to the nearest integer.<br>
      Example:<br><code>floor(4.8);</code><br>Output: <code>4</code></td>
    </tr>
    <tr>
      <td>round()</td>
      <td><code>round(number, precision=0, mode=PHP_ROUND_HALF_UP)</code></td>
      <td>Rounds a float to given precision. Default mode rounds halves up.<br>
      Example:<br><code>round(3.14159,2);</code><br>Output: <code>3.14</code></td>
    </tr>
    <tr><th colspan="3">Min / Max / Absolute Comparison</th></tr>
    <tr>
      <td>min()</td>
      <td><code>min(value1, value2, ...)</code></td>
      <td>Returns smallest value from arguments or array.<br>
      Example:<br><code>min(3,7,1);</code><br>Output: <code>1</code></td>
    </tr>
    <tr>
      <td>max()</td>
      <td><code>max(value1, value2, ...)</code></td>
      <td>Returns largest value from arguments or array.<br>
      Example:<br><code>max(3,7,1);</code><br>Output: <code>7</code></td>
    </tr>
    <tr><th colspan="3">Power / Exponent / Roots / Log</th></tr>
    <tr>
      <td>pow()</td>
      <td><code>pow(base, exp)</code></td>
      <td>Calculates base raised to power exp (<code>base**exp</code>).<br>
      Example:<br><code>pow(2,3);</code><br>Output: <code>8</code></td>
    </tr>
    <tr>
      <td>sqrt()</td>
      <td><code>sqrt(number)</code></td>
      <td>Square root of number. Returns NAN for negative numbers.<br>
      Example:<br><code>sqrt(16);</code><br>Output: <code>4</code></td>
    </tr>
    <tr>
      <td>exp()</td>
      <td><code>exp(number)</code></td>
      <td>Returns e raised to the power of number (e^number).<br>
      Example:<br><code>exp(1);</code><br>Output: <code>2.718281828459</code> (approx)</td>
    </tr>
    <tr>
      <td>log()</td>
      <td><code>log(number, base = M_E)</code></td>
      <td>Natural logarithm by default (base e). Optional second arg as base.<br>
      Example:<br><code>log(8,2);</code><br>Output: <code>3</code></td>
    </tr>
    <tr>
      <td>log10()</td>
      <td><code>log10(number)</code></td>
      <td>Base-10 logarithm.<br>
      Example:<br><code>log10(1000);</code><br>Output: <code>3</code></td>
    </tr>
    <tr><th colspan="3">Trigonometry</th></tr>
    <tr>
      <td>sin()</td>
      <td><code>sin(angle_in_radians)</code></td>
      <td>Returns sine of angle (radians).<br>
      Example:<br><code>sin(pi()/2);</code><br>Output: <code>1</code></td>
    </tr>
    <tr>
      <td>cos()</td>
      <td><code>cos(angle_in_radians)</code></td>
      <td>Returns cosine of angle (radians).<br>
      Example:<br><code>cos(0);</code><br>Output: <code>1</code></td>
    </tr>
    <tr>
      <td>tan()</td>
      <td><code>tan(angle_in_radians)</code></td>
      <td>Returns tangent of angle (radians).<br>
      Example:<br><code>tan(pi()/4);</code><br>Output: <code>1</code></td>
    </tr>
    <tr>
      <td>asin()</td>
      <td><code>asin(value)</code></td>
      <td>Inverse sine, returns angle in radians (value between -1 and 1).<br>
      Example:<br><code>asin(1);</code><br>Output: <code>1.57079632679</code> (pi/2)</td>
    </tr>
    <tr>
      <td>acos()</td>
      <td><code>acos(value)</code></td>
      <td>Inverse cosine, returns radians.<br>
      Example:<br><code>acos(1);</code><br>Output: <code>0</code></td>
    </tr>
    <tr>
      <td>atan()</td>
      <td><code>atan(value)</code></td>
      <td>Inverse tangent, returns radians.<br>
      Example:<br><code>atan(1);</code><br>Output: <code>0.78539816339</code> (pi/4)</td>
    </tr>
    <tr>
      <td>deg2rad()</td>
      <td><code>deg2rad(degrees)</code></td>
      <td>Converts degrees to radians.<br>
      Example:<br><code>deg2rad(180);</code><br>Output: <code>3.14159265359</code></td>
    </tr>
    <tr>
      <td>rad2deg()</td>
      <td><code>rad2deg(radians)</code></td>
      <td>Converts radians to degrees.<br>
      Example:<br><code>rad2deg(pi());</code><br>Output: <code>180</code></td>
    </tr>
    <tr>
      <td>hypot()</td>
      <td><code>hypot(x, y)</code></td>
      <td>Returns sqrt(x*x + y*y) — length of hypotenuse.<br>
      Example:<br><code>hypot(3,4);</code><br>Output: <code>5</code></td>
    </tr>
    <tr><th colspan="3">Modulo / Integer Division / Remainder</th></tr>
    <tr>
      <td>fmod()</td>
      <td><code>fmod(x, y)</code></td>
      <td>Floating-point remainder of x / y. Different from % for negatives sometimes.<br>
      Example:<br><code>fmod(5.5, 2);</code><br>Output: <code>1.5</code></td>
    </tr>
    <tr>
      <td>intdiv()</td>
      <td><code>intdiv(dividend, divisor)</code></td>
      <td>Integer division that returns int (PHP 7+).<br>
      Example:<br><code>intdiv(7,2);</code><br>Output: <code>3</code></td>
    </tr>
    <tr><th colspan="3">Random / Seeded Random</th></tr>
    <tr>
      <td>rand()</td>
      <td><code>rand(min, max)</code></td>
      <td>Generates pseudo-random integer (inclusive). If no args, default range. Use mt_rand for better generator.<br>
      Example:<br><code>rand(1,10);</code><br>Output: <code>7</code> (example)</td>
    </tr>
    <tr>
      <td>mt_rand()</td>
      <td><code>mt_rand(min, max)</code></td>
      <td>Mersenne Twister random generator — faster and better. Use for most cases (PHP 7.1+ mt_rand is alias of random_int in some builds).<br>
      Example:<br><code>mt_rand(1,6);</code><br>Output: <code>4</code> (example)</td>
    </tr>
    <tr>
      <td>srand()</td>
      <td><code>srand(seed)</code></td>
      <td>Seeds the random number generator (not usually necessary).<br>
      Example:<br><code>srand(123); rand(1,100);</code><br>Output: <code>... (deterministic)</code></td>
    </tr>
    <tr><th colspan="3">Constants / Helper</th></tr>
    <tr>
      <td>pi()</td>
      <td><code>pi()</code></td>
      <td>Returns value of π (pi).<br>
      Example:<br><code>pi();</code><br>Output: <code>3.1415926535898</code></td>
    </tr>
    <tr>
      <td>is_finite()</td>
      <td><code>is_finite(number)</code></td>
      <td>Checks if number is finite (not INF or NAN).<br>
      Example:<br><code>is_finite(1/0);</code><br>Output: <code>false</code></td>
    </tr>
    <tr>
      <td>is_infinite()</td>
      <td><code>is_infinite(number)</code></td>
      <td>Checks if number is infinite.<br>
      Example:<br><code>is_infinite(1/0);</code><br>Output: <code>true</code></td>
    </tr>
    <tr>
      <td>is_nan()</td>
      <td><code>is_nan(number)</code></td>
      <td>Checks if value is NaN (not a number).<br>
      Example:<br><code>is_nan(acos(2));</code><br>Output: <code>true</code></td>
    </tr>
    <tr><th colspan="3">Type Conversion / Formatting</th></tr>
    <tr>
      <td>intval()</td>
      <td><code>intval(mixed, base=10)</code></td>
      <td>Converts value to integer. Optional base for strings.<br>
      Example:<br><code>intval("15");</code><br>Output: <code>15</code></td>
    </tr>
    <tr>
      <td>floatval()</td>
      <td><code>floatval(mixed)</code></td>
      <td>Converts value to float/double.<br>
      Example:<br><code>floatval("3.14");</code><br>Output: <code>3.14</code></td>
    </tr>
    <tr>
      <td>number_format()</td>
      <td><code>number_format(number, decimals=0, dec_point='.', thousands_sep=',')</code></td>
      <td>Formats a number with grouped thousands and specified decimals.<br>
      Example:<br><code>number_format(1234.567,2);</code><br>Output: <code>1,234.57</code></td>
    </tr>
    <tr><th colspan="3">Arbitrary-precision / BCMath (if extension available)</th></tr>
    <tr>
      <td>bcadd()</td>
      <td><code>bcadd(string left, string right, scale=0)</code></td>
      <td>Adds two arbitrary-precision numbers represented as strings.<br>
      Example:<br><code>bcadd("1.234","2.001",3);</code><br>Output: <code>"3.235"</code></td>
    </tr>
    <tr>
      <td>bcsub()</td>
      <td><code>bcsub(left, right, scale=0)</code></td>
      <td>Subtract with arbitrary precision.<br>
      Example:<br><code>bcsub("5.5","2.2",1);</code><br>Output: <code>"3.3"</code></td>
    </tr>
    <tr>
      <td>bcmul()</td>
      <td><code>bcmul(left, right, scale=0)</code></td>
      <td>Multiply with arbitrary precision.<br>
      Example:<br><code>bcmul("2.5","4",2);</code><br>Output: <code>"10.00"</code></td>
    </tr>
    <tr>
      <td>bcdiv()</td>
      <td><code>bcdiv(left, right, scale=0)</code></td>
      <td>Divide with arbitrary precision.<br>
      Example:<br><code>bcdiv("5","2",2);</code><br>Output: <code>"2.50"</code></td>
    </tr>
    <tr>
      <td>bcpow()</td>
      <td><code>bcpow(base, exp, scale=0)</code></td>
      <td>Power with arbitrary precision.<br>
      Example:<br><code>bcpow("2","10",0);</code><br>Output: <code>"1024"</code></td>
    </tr>
    <tr>
      <td>bcmod()</td>
      <td><code>bcmod(left, right)</code></td>
      <td>Modulo for big numbers.<br>
      Example:<br><code>bcmod("10","3");</code><br>Output: <code>"1"</code></td>
    </tr>
    <tr>
      <td>bccomp()</td>
      <td><code>bccomp(left, right, scale=0)</code></td>
      <td>Compare two arbitrary-precision numbers. Returns -1, 0, 1.<br>
      Example:<br><code>bccomp("1.00","1.000",3);</code><br>Output: <code>0</code></td>
    </tr>
    <tr><th colspan="3">Misc / Useful Helpers</th></tr>
    <tr>
      <td>round() (repeated)</td>
      <td><code>round(number, precision)</code></td>
      <td>Already covered — useful for formatting and calculations.<br>
      Example:<br><code>round(2.675,2);</code><br>Output: <code>2.67</code> (note floating rounding behavior)</td>
    </tr>
    <tr>
      <td>gmp_* (if GMP extension)</td>
      <td><code>gmp_add, gmp_mul, gmp_pow, ...</code></td>
      <td>GMP provides fast arbitrary-precision math for integers. Usage requires extension.<br>
      Example:<br><code>gmp_add("12345678901234567890","1");</code><br>Output: <code>gmp number</code></td>
    </tr>

  </tbody>
</table>


## Date/Time functions.

<table>
  <thead>
    <tr>
      <th>Function Name</th>
      <th>Syntax</th>
      <th>Description + Example + Output</th>
    </tr>
  </thead>

  <tbody>
    <tr><th colspan="3">Getting Current Date & Time</th></tr>
    <tr>
      <td>date()</td>
      <td><code>date(format, timestamp = time())</code></td>
      <td>Returns a formatted date/time string.<br>
      Example:<br><code>date("Y-m-d H:i:s");</code><br>Output: <code>2025-01-10 14:32:10</code></td>
    </tr>
    <tr>
      <td>time()</td>
      <td><code>time()</code></td>
      <td>Returns current Unix timestamp (seconds since 1970).<br>
      Example:<br><code>time();</code><br>Output: <code>1736512134</code></td>
    </tr>
    <tr>
      <td>microtime()</td>
      <td><code>microtime(as_float = false)</code></td>
      <td>Returns current Unix timestamp with microseconds.<br>
      Example:<br><code>microtime(true);</code><br>Output: <code>1736512134.123456</code></td>
    </tr>
    <tr>
      <td>getdate()</td>
      <td><code>getdate(timestamp = time())</code></td>
      <td>Returns an array containing date/time info.<br>
      Example:<br><code>getdate();</code><br>Output: <code>["seconds"=>34,"minutes"=>12,"hours"=>14,...]</code></td>
    </tr>
    <tr>
      <td>gettimeofday()</td>
      <td><code>gettimeofday(as_float = false)</code></td>
      <td>Returns array with seconds + microseconds OR float.<br>
      Example:<br><code>gettimeofday(true);</code><br>Output: <code>1736512134.55433</code></td>
    </tr>
    <tr><th colspan="3">Creating Custom Timestamps</th></tr>
    <tr>
      <td>mktime()</td>
      <td><code>mktime(hour, minute, second, month, day, year)</code></td>
      <td>Creates a Unix timestamp for a specific date/time.<br>
      Example:<br><code>mktime(0,0,0,1,1,2025);</code><br>Output: <code>1735689600</code></td>
    </tr>
    <tr>
      <td>strtotime()</td>
      <td><code>strtotime(time_string)</code></td>
      <td>Converts English date/time text to timestamp.<br>
      Example:<br><code>strtotime("next Monday");</code><br>Output: <code>1736784000</code></td>
    </tr>
    <tr>
      <td>idate()</td>
      <td><code>idate(format, timestamp)</code></td>
      <td>Returns formatted date/time as integer.<br>
      Example:<br><code>idate("m");</code><br>Output: <code>01</code></td>
    </tr>
    <tr><th colspan="3">Formatting Dates</th></tr>
    <tr>
      <td>date_format()</td>
      <td><code>date_format(DateTimeObject, format)</code></td>
      <td>Formats a DateTime object.<br>
      Example:<br><code>$d = new DateTime(); echo date_format($d,"Y-m-d");</code><br>
      Output: <code>2025-01-10</code></td>
    </tr>
    <tr>
      <td>DateTime::format()</td>
      <td><code>$dt->format("Y-m-d H:i:s")</code></td>
      <td>Formats using object-oriented style.<br>
      Example:<br><code>$dt = new DateTime(); echo $dt->format("d M Y");</code><br>
      Output: <code>10 Jan 2025</code></td>
    </tr>
    <tr>
      <td>gmdate()</td>
      <td><code>gmdate(format, timestamp)</code></td>
      <td>Same as date() BUT in UTC timezone.<br>
      Example:<br><code>gmdate("Y-m-d H:i:s");</code><br>Output: <code>2025-01-10 09:02:22</code></td>
    </tr>
    <tr><th colspan="3">DateTime Object – Creating & Modifying Dates</th></tr>
    <tr>
      <td>DateTime()</td>
      <td><code>new DateTime(time_string = "now", timezone = null)</code></td>
      <td>Creates a DateTime object.<br>
      Example:<br><code>$dt = new DateTime("2025-01-01");</code><br>Output: DateTime object</td>
    </tr>
    <tr>
      <td>DateTime::createFromFormat()</td>
      <td><code>DateTime::createFromFormat(format, time_string)</code></td>
      <td>Creates DateTime from custom format.<br>
      Example:<br><code>DateTime::createFromFormat("d-m-Y","10-01-2025");</code></td>
    </tr>
    <tr>
      <td>DateTime::modify()</td>
      <td><code>$dt->modify("+1 day")</code></td>
      <td>Modifies existing DateTime.<br>
      Example:<br><code>$dt->modify("+2 weeks");</code></td>
    </tr>
    <tr>
      <td>DateTime::setDate()</td>
      <td><code>$dt->setDate(year, month, day)</code></td>
      <td>Changes the date of DateTime object.<br>
      Example:<br><code>$dt->setDate(2025,12,25);</code></td>
    </tr>
    <tr>
      <td>DateTime::setTime()</td>
      <td><code>$dt->setTime(hour, minute, second)</code></td>
      <td>Changes time of object.<br>
      Example:<br><code>$dt->setTime(12,30,00);</code></td>
    </tr>
    <tr><th colspan="3">Differences Between Dates</th></tr>
    <tr>
      <td>DateTime::diff()</td>
      <td><code>$dt1->diff($dt2)</code></td>
      <td>Returns difference as DateInterval object.<br>
      Example:<br><code>$d1=new DateTime("2025-01-01"); $d2=new DateTime("2025-01-10"); $diff=$d1->diff($d2);</code><br>Output: <code>9 days</code></td>
    </tr>
    <tr>
      <td>date_diff()</td>
      <td><code>date_diff(DateTime1, DateTime2)</code></td>
      <td>Procedural version of diff().<br>
      Example:<br><code>date_diff($d1,$d2);</code></td>
    </tr>
    <tr><th colspan="3">DateInterval (Durations)</th></tr>
    <tr>
      <td>DateInterval()</td>
      <td><code>new DateInterval("P2Y3M5D")</code></td>
      <td>Creates custom duration (P = period).<br>
      Example:<br><code>new DateInterval("P1Y2M");</code></td>
    </tr>
    <tr>
      <td>DateInterval::format()</td>
      <td><code>$interval->format("%y years %m months")</code></td>
      <td>Formats difference result.<br>
      Example:<br><code>$diff->format("%a days");</code></td>
    </tr>
    <tr><th colspan="3">Timezone Functions</th></tr>
    <tr>
      <td>date_default_timezone_set()</td>
      <td><code>date_default_timezone_set(timezone)</code></td>
      <td>Sets default timezone for script.<br>
      Example:<br><code>date_default_timezone_set("Asia/Kolkata");</code></td>
    </tr>
    <tr>
      <td>date_default_timezone_get()</td>
      <td><code>date_default_timezone_get()</code></td>
      <td>Returns current timezone.<br>
      Example:<br><code>date_default_timezone_get();</code></td>
    </tr>
    <tr>
      <td>DateTimeZone()</td>
      <td><code>new DateTimeZone("Asia/Kolkata")</code></td>
      <td>Creates timezone object.<br>
      Example:<br><code>$tz=new DateTimeZone("UTC");</code></td>
    </tr>
    <tr>
      <td>DateTime::setTimezone()</td>
      <td><code>$dt->setTimezone($tz)</code></td>
      <td>Changes timezone of DateTime object.<br>
      Example:<br><code>$dt->setTimezone(new DateTimeZone("UTC"));</code></td>
    </tr>
    <tr><th colspan="3">Validation & Parsing</th></tr>
    <tr>
      <td>checkdate()</td>
      <td><code>checkdate(month, day, year)</code></td>
      <td>Checks if date is valid.<br>
      Example:<br><code>checkdate(2,29,2025);</code><br>Output: <code>false</code></td>
    </tr>
    <tr>
      <td>date_parse()</td>
      <td><code>date_parse(date_string)</code></td>
      <td>Parses date string into array with details.<br>
      Example:<br><code>date_parse("2025-01-10");</code><br>Output: <code>["year"=>2025,"month"=>1,"day"=>10,...]</code></td>
    </tr>
    <tr>
      <td>date_parse_from_format()</td>
      <td><code>date_parse_from_format(format,string)</code></td>
      <td>Parses date using custom format.<br>
      Example:<br><code>date_parse_from_format("d/m/Y","10/01/2025");</code></td>
    </tr>
    <tr><th colspan="3">Misc Date Functions</th></tr>
    <tr>
      <td>localtime()</td>
      <td><code>localtime(timestamp, is_assoc=false)</code></td>
      <td>Returns array of local time components.<br>
      Example:<br><code>localtime(time(),true);</code></td>
    </tr>
    <tr>
      <td>date_sunrise()</td>
      <td><code>date_sunrise(timestamp, format, latitude, longitude)</code></td>
      <td>Returns sunrise time for a location.<br>
      Example:<br><code>date_sunrise(time(), SUNFUNCS_RET_STRING, 28.6, 77.2);</code></td>
    </tr>
    <tr>
      <td>date_sunset()</td>
      <td><code>date_sunset(timestamp, format, latitude, longitude)</code></td>
      <td>Returns sunset time for a location.<br>
      Example:<br><code>date_sunset(time(), SUNFUNCS_RET_STRING, 28.6, 77.2);</code></td>
    </tr>
    <tr>
      <td>date_timestamp_get()</td>
      <td><code>$dt->getTimestamp()</code></td>
      <td>Gets timestamp from DateTime object.<br>
      Example:<br><code>$dt->getTimestamp();</code></td>
    </tr>
    <tr>
      <td>date_timestamp_set()</td>
      <td><code>$dt->setTimestamp(unix_timestamp)</code></td>
      <td>Sets timestamp for DateTime object.<br>
      Example:<br><code>$dt->setTimestamp(1736512000);</code></td>
    </tr>
  </tbody>
</table>

## Session/Cookies functions

<table>
  <thead>
    <tr>
      <th>Function Name</th>
      <th>Syntax</th>
      <th>Description + Example + Output</th>
    </tr>
  </thead>
  <tbody>
    <tr><th colspan="3">Session Handling Functions</th></tr>
    <tr>
      <td>session_start()</td>
      <td><code>session_start()</code></td>
      <td>Starts a new session or resumes existing session. Must be called before HTML output.<br>
      Example:<br><code>session_start();</code><br>Output: Session begins and session ID is created.</td>
    </tr>
    <tr>
      <td>$_SESSION</td>
      <td><code>$_SESSION[key] = value</code></td>
      <td>Stores data in session (superglobal array).<br>
      Example:<br><code>$_SESSION["user"] = "Shivam";</code><br>Output: User value stored in session.</td>
    </tr>
    <tr>
      <td>session_id()</td>
      <td><code>session_id()</code></td>
      <td>Returns current session ID.<br>
      Example:<br><code>echo session_id();</code><br>Output: <code>hf73ks92jd92kd9...</code></td>
    </tr>
    <tr>
      <td>session_create_id()</td>
      <td><code>session_create_id(prefix)</code></td>
      <td>Creates a new unique session ID (without starting session).<br>
      Example:<br><code>session_create_id("user_");</code><br>Output: <code>user_64ff8e9abc23</code></td>
    </tr>
    <tr>
      <td>session_regenerate_id()</td>
      <td><code>session_regenerate_id(delete_old)</code></td>
      <td>Creates a new session ID to prevent session fixation attacks.<br>
      Example:<br><code>session_regenerate_id(true);</code><br>Output: Old ID replaced with new ID.</td>
    </tr>
    <tr>
      <td>session_unset()</td>
      <td><code>session_unset()</code></td>
      <td>Removes all session variables but keeps the session active.<br>
      Example:<br><code>session_unset();</code><br>Output: <code>$_SESSION</code> becomes empty.</td>
    </tr>
    <tr>
      <td>session_destroy()</td>
      <td><code>session_destroy()</code></td>
      <td>Destroys the session completely (ID removed).<br>
      Example:<br><code>session_destroy();</code><br>Output: Session deleted.</td>
    </tr>
    <tr>
      <td>session_get_cookie_params()</td>
      <td><code>session_get_cookie_params()</code></td>
      <td>Returns cookie settings used by session.<br>
      Example:<br><code>print_r(session_get_cookie_params());</code></td>
    </tr>
    <tr>
      <td>session_set_cookie_params()</td>
      <td><code>session_set_cookie_params(lifetime, path, domain, secure, httponly)</code></td>
      <td>Sets cookie parameters for future sessions.<br>
      Example:<br><code>session_set_cookie_params(3600, "/");</code></td>
    </tr>
    <tr>
      <td>session_status()</td>
      <td><code>session_status()</code></td>
      <td>Returns current session status:<br>
      0 = disabled, 1 = none, 2 = active.<br>
      Example:<br><code>session_status();</code><br>Output: <code>2</code> (if active)</td>
    </tr>
    <tr>
      <td>session_cache_limiter()</td>
      <td><code>session_cache_limiter(setting)</code></td>
      <td>Sets cache control headers for session pages.<br>
      Example:<br><code>session_cache_limiter("private");</code></td>
    </tr>
    <tr>
      <td>session_cache_expire()</td>
      <td><code>session_cache_expire(minutes)</code></td>
      <td>Sets or gets the session cache expiration time.<br>
      Example:<br><code>session_cache_expire(60);</code></td>
    </tr>
    <tr><th colspan="3">Cookie Handling Functions</th></tr>
    <tr>
      <td>setcookie()</td>
      <td><code>setcookie(name, value, expire, path, domain, secure, httponly)</code></td>
      <td>Creates or updates a cookie. Must be sent before HTML output.<br>
      Example:<br><code>setcookie("username","Shivam",time()+3600,"/");</code><br>Output: Cookie stored for 1 hour.</td>
    </tr>
    <tr>
      <td>$_COOKIE</td>
      <td><code>$_COOKIE[name]</code></td>
      <td>Superglobal array used to access cookies.<br>
      Example:<br><code>echo $_COOKIE["username"];</code><br>Output: <code>Shivam</code></td>
    </tr>
    <tr>
      <td>setrawcookie()</td>
      <td><code>setrawcookie(name, value, expire, path, domain, secure, httponly)</code></td>
      <td>Sets cookie WITHOUT URL encoding the value.<br>
      Example:<br><code>setrawcookie("data","a=b&c=d");</code></td>
    </tr>
    <tr>
      <td>filter_input(INPUT_COOKIE, ...)</td>
      <td><code>filter_input(INPUT_COOKIE, name, filter)</code></td>
      <td>Gets cookie value with filters (recommended for security).<br>
      Example:<br><code>filter_input(INPUT_COOKIE,"username",FILTER_SANITIZE_STRING);</code></td>
    </tr>
    <tr>
      <td>setcookie() – delete</td>
      <td><code>setcookie(name,"",time()-3600)</code></td>
      <td>Deletes a cookie by setting expire time in the past.<br>
      Example:<br><code>setcookie("username","",time()-3600);</code><br>Output: Cookie removed.</td>
    </tr>
    <tr><th colspan="3">Superglobals Related to Sessions & Cookies</th></tr>
    <tr>
      <td>$_SESSION</td>
      <td><code>$_SESSION[key]</code></td>
      <td>Stores session data.<br>
      Example:<br><code>$_SESSION["id"]=10;</code></td>
    </tr>
    <tr>
      <td>$_COOKIE</td>
      <td><code>$_COOKIE[key]</code></td>
      <td>Reads cookie value.<br>
      Example:<br><code>$_COOKIE["theme"];</code></td>
    </tr>
    <tr>
      <td>$_SERVER["REQUEST_TIME"]</td>
      <td><code>$_SERVER["REQUEST_TIME"]</code></td>
      <td>Timestamp when request started.<br>
      Example:<br><code>echo $_SERVER["REQUEST_TIME"];</code></td>
    </tr>
  </tbody>
</table>

## PHP Error/Exception Handling Functions

<table>
  <thead>
    <tr>
      <th>Function / Feature</th>
      <th>Syntax</th>
      <th>Description + Example + Output</th>
    </tr>
  </thead>
  <tbody>
    <tr><th colspan="3">Configuration & Reporting</th></tr>
    <tr>
      <td>error_reporting()</td>
      <td><code>error_reporting(level)</code></td>
      <td>Sets which PHP errors are reported. Use constants like <code>E_ALL</code>, <code>E_WARNING</code>. Without arg it returns current level.<br>
      Example:<br><code>error_reporting(E_ALL);</code><br>Output: no direct output; controls which errors are shown/logged (returns previous level if used with arg).</td>
    </tr>
    <tr>
      <td>ini_set()</td>
      <td><code>ini_set("display_errors","1"|"0")</code></td>
      <td>Change php.ini settings at runtime (common flags: <code>display_errors</code>, <code>log_errors</code>, <code>error_log</code>).<br>
      Example:<br><code>ini_set("display_errors","1"); ini_set("log_errors","1");</code><br>Output: no direct output; errors will display and be logged per settings.</td>
    </tr>
    <tr>
      <td>ini_get()</td>
      <td><code>ini_get("setting")</code></td>
      <td>Get current value of a php.ini setting.<br>
      Example:<br><code>ini_get("display_errors");</code><br>Output: <code>"1"</code> (if enabled)</td>
    </tr>
    <tr><th colspan="3">Custom Error Handlers</th></tr>
    <tr>
      <td>set_error_handler()</td>
      <td><code>set_error_handler(callable $handler, int $error_types = E_ALL)</code></td>
      <td>Registers a user-defined function to handle non-fatal errors. Handler signature: <code>function($errno, $errstr, $errfile, $errline)</code>.<br>
      Example:<br><code>set_error_handler(function($n,$s,$f,$l){ echo "Custom error: $s on $f:$l"; });</code><br>Output (when an E_WARNING occurs): <code>Custom error: ... on file.php:10</code></td>
    </tr>
    <tr>
      <td>restore_error_handler()</td>
      <td><code>restore_error_handler()</code></td>
      <td>Restores the previous error handler (undoes set_error_handler).<br>
      Example:<br><code>restore_error_handler();</code><br>Output: no direct output; handler restored to previous/default.</td>
    </tr>
    <tr><th colspan="3">Triggering & Logging Errors</th></tr>
    <tr>
      <td>trigger_error()</td>
      <td><code>trigger_error(message, error_type = E_USER_NOTICE)</code></td>
      <td>Programmatically raises a user-level error (E_USER_NOTICE, E_USER_WARNING, E_USER_ERROR). Useful for custom validation.<br>
      Example:<br><code>trigger_error("Invalid input", E_USER_WARNING);</code><br>Output: Warning shown/logged: <code>PHP Warning: Invalid input</code></td>
    </tr>
    <tr>
      <td>user_error()</td>
      <td><code>user_error(message, error_type)</code></td>
      <td>Alias of <code>trigger_error()</code> (same behavior).<br>
      Example:<br><code>user_error("Something bad", E_USER_NOTICE);</code><br>Output: Notice displayed or logged depending on config.</td>
    </tr>
    <tr>
      <td>error_log()</td>
      <td><code>error_log(message, message_type = 0, destination = null)</code></td>
      <td>Send an error message to server log, file, or email. <code>message_type</code> controls destination.<br>
      Example:<br><code>error_log("Payment failed", 3, "/tmp/myapp.log");</code><br>Output: writes <code>Payment failed</code> to <code>/tmp/myapp.log</code></td>
    </tr>
    <tr><th colspan="3">Shutdown / Fatal Errors Handling</th></tr>
    <tr>
      <td>register_shutdown_function()</td>
      <td><code>register_shutdown_function(callable)</code></td>
      <td>Registers a callback executed at script shutdown — useful to catch fatal errors via <code>error_get_last()</code> inside callback.<br>
      Example:<br><code>register_shutdown_function(function(){ $e = error_get_last(); if($e) echo "Shutdown error: {$e['message']}"; });</code><br>Output (on fatal): <code>Shutdown error: ...</code></td>
    </tr>
    <tr>
      <td>error_get_last()</td>
      <td><code>error_get_last()</code></td>
      <td>Returns the last error as an array (<code>type,message,file,line</code>) or <code>null</code>. Commonly used inside a shutdown function.<br>
      Example:<br><code>$e = error_get_last(); print_r($e);</code><br>Output: <code>Array ( [type]=>1 [message]=>"Fatal ...")</code></td>
    </tr>
    <tr>
      <td>error_clear_last()</td>
      <td><code>error_clear_last()</code></td>
      <td>Clears the most recent error (useful before calling code that might set one).<br>
      Example:<br><code>error_clear_last();</code><br>Output: no direct output; last error cleared.</td>
    </tr>
    <tr><th colspan="3">Exceptions & Exception Handlers</th></tr>
    <tr>
      <td>try / catch / finally</td>
      <td><code>try { ... } catch (Exception $e) { ... } finally { ... }</code></td>
      <td>Language-level construct to catch exceptions. Use <code>throw new Exception()</code> to raise.<br>
      Example:<br><code>try { throw new Exception("Fail"); } catch (Exception $e) { echo $e->getMessage(); }</code><br>Output: <code>Fail</code></td>
    </tr>
    <tr>
      <td>set_exception_handler()</td>
      <td><code>set_exception_handler(callable $handler)</code></td>
      <td>Sets a global handler for uncaught exceptions. Handler receives the Throwable object.<br>
      Example:<br><code>set_exception_handler(function($e){ echo "Uncaught: ".$e->getMessage(); });</code><br>Output (if uncaught): <code>Uncaught: ...</code></td>
    </tr>
    <tr>
      <td>restore_exception_handler()</td>
      <td><code>restore_exception_handler()</code></td>
      <td>Restores previous exception handler (undoes set_exception_handler()).<br>
      Example:<br><code>restore_exception_handler();</code><br>Output: no direct output; handler restored.</td>
    </tr>
    <tr><th colspan="3">Throwable / Exception Object Methods</th></tr>
    <tr>
      <td>getMessage()</td>
      <td><code>$e->getMessage()</code></td>
      <td>Returns exception message.<br>
      Example:<br><code>catch(Exception $e){ echo $e->getMessage(); }</code><br>Output: message string</td>
    </tr>
    <tr>
      <td>getCode()</td>
      <td><code>$e->getCode()</code></td>
      <td>Returns user-supplied exception code (int/string).<br>
      Example:<br><code>$e->getCode();</code><br>Output: <code>0</code> (default)</td>
    </tr>
    <tr>
      <td>getFile()</td>
      <td><code>$e->getFile()</code></td>
      <td>Returns filename where exception was thrown.<br>
      Example:<br><code>echo $e->getFile();</code><br>Output: <code>/path/to/file.php</code></td>
    </tr>
    <tr>
      <td>getLine()</td>
      <td><code>$e->getLine()</code></td>
      <td>Returns line number where exception thrown.<br>
      Example:<br><code>echo $e->getLine();</code><br>Output: <code>42</code></td>
    </tr>
    <tr>
      <td>getTrace()</td>
      <td><code>$e->getTrace()</code></td>
      <td>Returns array stack trace. Useful for structured logging.<br>
      Example:<br><code>print_r($e->getTrace());</code><br>Output: stack trace array</td>
    </tr>
    <tr>
      <td>getTraceAsString()</td>
      <td><code>$e->getTraceAsString()</code></td>
      <td>Returns trace as a formatted string.<br>
      Example:<br><code>echo $e->getTraceAsString();</code><br>Output: human-readable stack trace</td>
    </tr>
    <tr>
      <td>__toString()</td>
      <td><code>(string) $e</code></td>
      <td>Converts Exception to string containing message, code, file, line and stack trace.<br>
      Example:<br><code>echo (string)$e;</code><br>Output: concatenated exception info</td>
    </tr>
    <tr><th colspan="3">Error & Throwable Classes (PHP 7+)</th></tr>
    <tr>
      <td>Error / Throwable</td>
      <td><code>Throwable, Error, Exception</code></td>
      <td>PHP 7 introduced <code>Throwable</code> interface. <code>Error</code> represents engine (fatal) errors and can be caught like exceptions.<br>
      Example:<br><code>try { /* type error */ } catch (Error $err) { echo $err->getMessage(); }</code><br>Output: message from Error instance</td>
    </tr>
    <tr><th colspan="3">Debugging Helpers</th></tr>
    <tr>
      <td>debug_backtrace()</td>
      <td><code>debug_backtrace(options=DEBUG_BACKTRACE_PROVIDE_OBJECT, limit=0)</code></td>
      <td>Returns an array describing the call stack — useful when logging errors manually.<br>
      Example:<br><code>print_r(debug_backtrace());</code><br>Output: array of stack frames</td>
    </tr>
    <tr>
      <td>debug_print_backtrace()</td>
      <td><code>debug_print_backtrace()</code></td>
      <td>Prints a formatted backtrace directly (good for quick debug output).<br>
      Example:<br><code>debug_print_backtrace();</code><br>Output: printed stack trace</td>
    </tr>
    <tr><th colspan="3">Error Inspection & Utilities</th></tr>
    <tr>
      <td>display_errors / log_errors</td>
      <td><code>ini_set("display_errors","1") / ini_set("log_errors","1")</code></td>
      <td>Control whether errors are shown to user or logged. Use <code>display_errors=0</code> in production and <code>log_errors=1</code> to capture them in logs.<br>
      Example:<br><code>ini_set("display_errors","0"); ini_set("log_errors","1");</code><br>Output: no visible errors; recorded in error log</td>
    </tr>
    <tr>
      <td>error_log (revisited)</td>
      <td><code>error_log(string)</code></td>
      <td>Use for custom logging of exception/error details (combine with exception methods and debug_backtrace()).<br>
      Example:<br><code>error_log($e->getMessage()." at ".$e->getFile().":".$e->getLine());</code><br>Output: entry in configured error log</td>
    </tr>
    <tr><th colspan="3">Best Practices & Notes</th></tr>
    <tr>
      <td colspan="3">
        - In production: <code>error_reporting(E_ALL)</code> + <code>ini_set("display_errors", "0")</code> + <code>ini_set("log_errors","1")</code>. <br>
        - Use <code>set_error_handler()</code> to convert notices/warnings to Exceptions if you want unified exception-based flow.<br>
        - Register <code>set_exception_handler()</code> and <code>register_shutdown_function()</code> to catch uncaught exceptions and fatal errors and to log them centrally.<br>
        - Never expose raw error messages to end users (leaks info). Log full details and show generic messages to users.<br>
        - Learn difference: <code>error_get_last()</code> + shutdown function is used to handle fatal errors that normally bypass custom error handlers.
      </td>
    </tr>
  </tbody>
</table>
