# Python for Generative & Agentic AI — Consolidated Notes

*Covers: Variables & Datatypes, Loops & Conditions, Data Structures, Functions, Modules & Classes, NumPy & Pandas, Reading API Data, Data Visualization.*

---

## 1. Why Python for Gen AI

Python dominates AI/ML work because of:
- Easy, readable syntax → faster debugging and collaboration
- Fast prototyping → quick experimentation with models/agents
- OOP support → reusable, modular code (e.g., agent classes)
- Interpreted → no compile step, rapid iteration
- Rich ecosystem: **NumPy, Pandas, Scikit-learn, PyTorch, Transformers, LangChain, FastAPI**

> As a PHP developer, the biggest mental shift: Python uses **indentation** (not `{}`) to define code blocks, and variables need no `$` prefix or type declaration.

---

## 2. Variables & Data Types

A variable is a named container for a value. No explicit type declaration needed — Python infers it.

**Naming rules:**
1. Must start with a letter or underscore — never a digit (`1name` ❌, `_name` ✅)
2. After the first character, letters/digits/underscores are all fine (`name_1` ✅)
3. No special characters (`@ # $ % !`) — `name_` ✅, `name!` ❌
4. Case-sensitive: `Age` and `age` are different variables
5. Cannot be a reserved keyword (`if`, `class`, `for`...) or shadow a builtin (`list`, `sum`, `dict`) as a name
6. Use `import keyword; keyword.kwlist` to list all 35 reserved words

**Core data types:**

| Type | Example | Notes |
|---|---|---|
| `str` | `"hello"`, `'123'` | single/double/triple quotes |
| `int` | `42`, `-7` | whole numbers |
| `float` | `3.14`, `-153.5` | decimals |
| `bool` | `True`, `False` | result of comparisons |

Use `type(variable)` to check a variable's type.

### Practice Questions — Variables & Datatypes
1. Which of these is a **valid** Python variable name: `2total`, `total_2`, `total-2`, `total 2`?
2. What will `type(345 > 230)` return?
3. Why does `if = 'INTTRVU'` throw a `SyntaxError`?
4. What is the output of:
   ```python
   x = 10
   y = "10"
   print(type(x) == type(y))
   ```
5. Name two ways in which Python's approach to variable typing differs from PHP's.

<details><summary>Answers</summary>

1. `total_2` (others start with a digit, or contain `-`/space, both invalid)
2. `bool`
3. `if` is a reserved keyword and cannot be used as a variable name
4. `False` (`x` is `int`, `y` is `str`)
5. Python is dynamically typed with no `$` sigil or `var`/type declaration; type is inferred at assignment and can change if reassigned (duck typing) — PHP variables are prefixed with `$` and (outside strict typing) are also dynamic, but Python has no sigil and enforces stricter indentation-based blocks.
</details>

---

## 3. Operators

| Category | Operators | Example |
|---|---|---|
| Arithmetic | `+ - * / // % **` | `10 // 3 = 3`, `10 % 3 = 1`, `2 ** 3 = 8` |
| Comparison | `== != > < >= <=` | `5 == 5 → True` |
| Assignment | `= += -= *=` | `a += 3` → `a = a + 3` |
| Logical | `and`, `or`, `not` | `(5>3) and (10>5) → True` |
| Identity | `is`, `is not` | compares memory location, not value |
| Membership | `in`, `not in` | `"apple" in fruits` |

**Common trap:** `/` always returns a `float` in Python 3, even `10 / 2 = 5.0`. Use `//` for integer (floor) division.

### Practice Questions — Operators
1. What does `17 // 5` evaluate to? What about `17 % 5`?
2. What's the difference between `==` and `is`?
3. Evaluate: `not (5 > 10) or (3 == 3)`
4. What does `a *= 4` expand to?

<details><summary>Answers</summary>

1. `17 // 5 = 3`, `17 % 5 = 2`
2. `==` compares **values**; `is` compares whether two variables point to the **same object in memory**
3. `True` (`not False` → `True`, then `True or True` → `True`)
4. `a = a * 4`
</details>

---

## 4. Conditions & Loops

**if / elif / else** — runs a block only when a condition is true. Indentation defines the block (typically 4 spaces).

```python
if x > 5:
    print("x is greater than 5")
elif x == 5:
    print("x is equal to 5")
else:
    print("x is less than 5")
```

`pass` is a no-op placeholder used where a statement is syntactically required.

**for loop** — iterates over a sequence (list, string, `range()`):
```python
for k in range(2, 11, 2):   # start, stop(exclusive), step
    print(k)
```
`range(10)` → 0 to 9. `range(len(my_list))` is a common pattern to loop with an index.

**Nested loops** — a loop inside another loop; useful for combining two sequences (e.g., every mark × every multiplier).

### Practice Questions — Loops & Conditions
1. What values does `range(2, 11, 2)` produce?
2. Rewrite this using a single `for` loop over the list directly, without an index:
   ```python
   marks = [85, 88, 67]
   for i in range(len(marks)):
       print(marks[i])
   ```
3. What is printed by:
   ```python
   x = 5
   if x > 5:
       print("A")
   elif x >= 5:
       print("B")
   else:
       print("C")
   ```
4. Write a loop that prints only the even numbers from a list `[1,2,3,4,5,6]`.
5. Why would forgetting to indent the body of an `if` statement cause an error in Python (unlike PHP)?

<details><summary>Answers</summary>

1. `2, 4, 6, 8, 10`
2. `for mark in marks: print(mark)`
3. `"B"`
4. ```python
   nums = [1,2,3,4,5,6]
   for n in nums:
       if n % 2 == 0:
           print(n)
   ```
5. Python uses indentation itself to define block scope (no `{}`), so an unindented or inconsistently indented line is a syntax error — in PHP, braces define scope and whitespace is cosmetic.
</details>

---

## 5. Data Structures

| Structure | Syntax | Ordered? | Mutable? | Duplicates? |
|---|---|---|---|---|
| **List** | `[1, 2, 'a']` | Yes | Yes | Yes |
| **Tuple** | `(1, 2, 'a')` | Yes | No | Yes |
| **Set** | `{1, 2, 'a'}` | No | Yes (add/remove) | No |
| **Dict** | `{'k': 'v'}` | Yes (3.7+) | Yes | No duplicate keys |

**Lists** — most common; key methods: `.insert(index, val)`, `.remove(val)`, `del list[i]`, `.sort()` / `.sort(reverse=True)`.

**Tuples** — immutable; use when data shouldn't change (e.g., coordinates, config that shouldn't be reassigned).

**Sets** — unordered, no duplicates; good for membership tests and de-duplication. `.remove()` raises an error if the item isn't found.

**Dictionaries** — key-value pairs. Access via `dict['key']` or safer `dict.get('key')`. Methods: `.keys()`, `.values()`, `.pop('key')`. If a duplicate key is written in a literal, only the **last** value is kept.

### Practice Questions — Data Structures
1. Which structure would you use to store a fixed set of (latitude, longitude) coordinates that must never change?
2. Given `d = {"a": 1, "a": 2}`, what is `d["a"]`?
3. What's the difference between `.remove()` and `del` on a list?
4. Why can't you do `my_tuple[0] = 'new_value'`?
5. Convert this list to a set to remove duplicates: `[1, 2, 2, 3, 3, 3]`
6. What does `dictionary.get("missing_key")` return if the key doesn't exist (vs. `dictionary["missing_key"]`)?

<details><summary>Answers</summary>

1. A tuple
2. `2` (later duplicate key overwrites the earlier one)
3. `.remove(value)` deletes by **value** (first match); `del list[index]` deletes by **index**
4. Tuples are immutable — item assignment isn't supported
5. `set([1, 2, 2, 3, 3, 3])` → `{1, 2, 3}`
6. `.get()` returns `None` (or a default you specify) instead of raising a `KeyError`
</details>

---

## 6. Functions

Defined with `def`; called by name + parentheses.

```python
def add_numbers(number_1, number_2):
    result = number_1 + number_2
    return result
```

**Argument types:**
- **Positional** — order matters: `add_numbers(10, 7)`
- **Default** — `def add_numbers(number_1=1, number_2=19):` → callable with zero args
- **`*args`** — arbitrary positional args, collected as a **tuple**
- **`**kwargs`** — arbitrary keyword args, collected as a **dict**

**Return values:** a function can return nothing (`None`), one value, or multiple values (returned as a tuple, unpacked on assignment):
```python
def add_multiply(a, b):
    return a + b, a * b

total, product = add_multiply(100, 50)
```
⚠️ Unpacking `total, add = add_numbers(100, 50)` fails with `TypeError: cannot unpack non-iterable int` if the function returns a single value, not two.

### Practice Questions — Functions
1. What is the difference between a parameter and an argument?
2. What type is `args` inside a function defined as `def f(*args):`?
3. Will `add_numbers(a=1, b=2)` work on a function defined as `def add_numbers(*args):`? Why/why not?
4. Write a function `describe_person(name, city="Unknown", **extra)` and call it with `name="Rohit"`, `city="Pune"`, `age=30`. What does `extra` contain?
5. Why does unpacking `x, y = my_func()` fail if `my_func` only has a bare `return result`?

<details><summary>Answers</summary>

1. A **parameter** is the placeholder in the function definition; an **argument** is the actual value passed when calling the function.
2. `tuple`
3. No — `*args` only accepts positional arguments; keyword arguments like `a=1` raise `TypeError: unexpected keyword argument`. You'd need `**kwargs` for that.
4. `extra` = `{"age": 30}` (a dict of any keyword args not matched to named parameters)
5. Because `return result` returns a single object; you can't unpack a non-iterable single value into two variables.
</details>

---

## 7. Modules & Classes (OOP)

**Modules** — a `.py` file of reusable functions/classes, imported via `import module_name` or `import module_name as alias`. Example: `calculations.py` defines `add_numbers`, `substract_numbers`, `multiply_numbers`, imported as `import calculations as calc; calc.add_numbers(10, 100)`. `help(module)` shows its docstring and function signatures.

**Classes** — blueprint for objects, combining data (attributes) and behavior (methods).
```python
class Person:
    def __init__(self, name, city, current_age):
        self.name = name
        self.city = city
        self.age = current_age

    def retirement_calculator(self, retirement_age):
        return retirement_age - self.age

new_person = Person("Rohit", "Pune", 33)
print(new_person.name)                          # attribute access
new_person.retirement_calculator(58)             # method call
```
- `__init__` is the **constructor**, auto-run when an object is created.
- `self` refers to the specific object instance — always the first parameter of instance methods.
- Each object created from a class has its **own copy** of the instance attributes (e.g., `new_person` and `new_person_another` have independent `.name` values).

### Practice Questions — Modules & Classes
1. What is the purpose of `__init__` in a class?
2. Why must every instance method (other than static methods) include `self` as its first parameter?
3. If you create two `Person` objects, `p1` and `p2`, and change `p1.name`, does `p2.name` change too? Why/why not?
4. What's the PHP OOP equivalent of Python's `__init__` method?
5. Write a `BankAccount` class with `__init__(self, owner, balance=0)` and a method `deposit(self, amount)` that adds to the balance and returns the new balance.

<details><summary>Answers</summary>

1. It's the constructor — code that runs automatically whenever a new object of the class is created, typically to set initial attribute values.
2. `self` lets the method access and modify the specific instance's own attributes; without it, Python wouldn't know which object's data to operate on.
3. No — each object has independent attribute storage; changing `p1.name` has no effect on `p2.name`.
4. PHP's `__construct()` method.
5. ```python
   class BankAccount:
       def __init__(self, owner, balance=0):
           self.owner = owner
           self.balance = balance

       def deposit(self, amount):
           self.balance += amount
           return self.balance
   ```
</details>

---

## 8. NumPy & Pandas (core AI/ML data tools)

**NumPy** — efficient numerical arrays; the backbone of embeddings, model inputs/outputs.
```python
import numpy as np
embedding = np.array([0.5, 0.2, -0.3, 0.8])
embedding.shape          # (4,)
data = np.array([[1,2,3],[4,5,6]])
data.reshape(3, 2)       # change dimensions (same total elements)
arr.mean(), arr.max()    # aggregate stats
```

**Pandas** — tabular data (DataFrames), like a spreadsheet in code.
```python
import pandas as pd
df = pd.DataFrame({'rating': [5,2,5,3,5], 'sentiment': ['pos','neg','pos','neu','pos']})

df.head(3)                          # first 3 rows
df.shape, df.columns.tolist()       # dimensions, column names
df.describe()                       # stats summary
df[df['rating'] >= 4]               # filter (like SQL WHERE)
df.groupby('sentiment')['rating'].mean()   # aggregate by group

df.isnull().sum()                   # count missing values per column
df.dropna()                         # drop rows with any missing value
df.fillna(0)                        # replace missing values

pd.read_csv('file.csv')             # load data
```

### Practice Questions — NumPy & Pandas
1. What's the difference between a NumPy array's `.shape` and its length via `len()`?
2. Given `arr = np.array([1,2,3,4,5,6])`, what does `arr.reshape(2,3)` produce?
3. Write a Pandas filter to select rows of `df` where `rating` equals exactly `5`.
4. What's the difference between `df.dropna()` and `df.fillna(0)`?
5. Using the `Housing.csv` columns (`price, area, bedrooms, bathrooms, stories, mainroad, guestroom, basement, hotwaterheating, airconditioning, parking, prefarea, furnishingstatus`), write the Pandas code to find the **average price grouped by `furnishingstatus`**.
6. How would you find how many houses have more than 3 bedrooms?

<details><summary>Answers</summary>

1. `.shape` gives dimensions along every axis as a tuple, e.g. `(3, 4)` for a 2D array; `len()` on a NumPy array only gives the size of the **first** axis.
2. ```
   [[1, 2, 3],
    [4, 5, 6]]
   ```
3. `df[df['rating'] == 5]`
4. `.dropna()` removes rows containing missing values; `.fillna(0)` keeps all rows but replaces missing values with `0`.
5. ```python
   df = pd.read_csv('Housing.csv')
   df.groupby('furnishingstatus')['price'].mean()
   ```
6. ```python
   len(df[df['bedrooms'] > 3])
   ```
</details>

---

## 9. Reading Data from an API

Pattern for pulling live/external data (e.g., for an AI agent to fetch tool results):
```python
import requests, json
from pandas import json_normalize

response = requests.get("https://api.example.com/data", allow_redirects=True)
print(response.headers.get('content-type'))     # confirm it's JSON

content = response.content                       # raw bytes
data = json.loads(content)                        # parse JSON string → Python dict
data = json_normalize(data)                        # flatten nested dict → DataFrame

# If a specific key holds a list of records, build a clean DataFrame from it:
dataframe = pd.DataFrame.from_dict(data['data'][0])
```

Key ideas:
- `requests.get()` performs the HTTP call; `.content` gives raw bytes, `.json()` (alternative) parses directly.
- `json.loads()` converts a JSON **string** into a Python `dict`/`list`.
- `json_normalize()` is essential when API responses have nested objects (e.g., `meta.fund_house`, `meta.scheme_type` become flat columns).

### Practice Questions — APIs
1. What's the difference between `response.content` and `response.json()`?
2. Why use `json_normalize()` instead of `pd.DataFrame(data)` directly on a nested API response?
3. What does `response.headers.get('content-type')` tell you, and why check it before parsing?
4. Write the code to check if an API call succeeded before parsing (`response.status_code == 200`).

<details><summary>Answers</summary>

1. `.content` returns the raw response body as bytes (needs manual `json.loads()`); `.json()` automatically parses the body into a Python dict/list.
2. Nested JSON (e.g., `{"meta": {"fund_house": "..."}}`) creates dict-of-dicts; `json_normalize()` flattens nested keys into dotted column names (`meta.fund_house`), which `pd.DataFrame()` alone won't do cleanly.
3. It confirms the server actually returned JSON (`application/json`) rather than HTML/an error page, so `json.loads()` won't fail unexpectedly.
4. ```python
   if response.status_code == 200:
       data = response.json()
   else:
       print("Request failed:", response.status_code)
   ```
</details>

---

## 10. Data Visualization

Two main libraries covered:
- **Seaborn** (`sns`) — quick, beautiful statistical plots, tightly integrated with Pandas.
- **Plotly Express** (`px`) — interactive charts (hover, zoom), good for dashboards/reports.

| Goal | Chart | Example call |
|---|---|---|
| Compare 2 numeric variables | Scatter | `sns.scatterplot(data=df, x='cost', y='accuracy', hue='model')` |
| Compare categories | Bar | `sns.barplot(data=df, x='model', y='accuracy')` |
| Show distribution/spread | Box plot | `sns.boxplot(data=df, x='task', y='accuracy')` |
| Show patterns across 2 dimensions | Heatmap | `sns.heatmap(pivot_table)` |
| Track a trend over time | Line | `sns.lineplot(data=df, x='epoch', y='accuracy', hue='dataset')` |
| Interactive grouped comparison | Plotly bar | `px.bar(df, x='task', y='accuracy', color='model', barmode='group')` |

**Chart-choice rule of thumb:**
- Comparing values → **bar**
- Showing trend over time → **line**
- Comparing two variables → **scatter**
- Showing distribution → **box plot**
- Showing 2D pattern/correlation → **heatmap**

### Practice Questions — Visualization
1. You want to compare the average `price` of houses in the `Housing.csv` dataset across `furnishingstatus` categories. Which chart type fits best, and why?
2. What's the purpose of a box plot that a bar chart can't show?
3. When would you prefer Plotly over Seaborn?
4. Write the Seaborn call to plot `area` (x) vs `price` (y) as a scatter plot from the housing data, colored by `airconditioning`.
5. What does a heatmap need as input (what shape of data)?

<details><summary>Answers</summary>

1. A **bar chart** — it's a category-to-category value comparison (mean price per furnishing type).
2. A box plot shows the spread, median, and outliers of a distribution — a bar chart (usually just a mean) hides variance and outliers.
3. When you need interactivity (hover tooltips, zoom, dynamic filtering) — e.g., in a shareable report or dashboard.
4. ```python
   sns.scatterplot(data=housing_df, x='area', y='price', hue='airconditioning')
   ```
5. A **pivot table** / 2D matrix — rows and columns as categories, cell values as the numeric measure (e.g., `pivot_table(values='accuracy', index='model', columns='task')`).
</details>

---

## Quick Reference: Common Pitfalls (from your notebooks)

- `1name = 5` → `SyntaxError` (names can't start with a digit)
- `add_numbers()` on a function with no defaults → `TypeError: missing positional arguments`
- Unpacking `a, b = func()` when `func` returns a single value → `TypeError: cannot unpack non-iterable`
- `my_tuple[0] = 'x'` → `TypeError` (tuples are immutable)
- Duplicate dict keys in a literal → only the last value survives
- `.remove()` on a set/list raises an error if the value isn't present (`.discard()` on sets is the safe version)
- Forgetting `content-type` / status checks before `json.loads()` on an API response → hard-to-debug parsing errors
