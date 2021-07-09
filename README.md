# Python Dictionary Demo
Table of Contents
=================

* [Terminology](#terminology)
* [Key/Value pairs definition](#keyvalue-pairs-definition)
* [{ }, Dict notation, curly braces](#--dict-notation-curly-braces)
* [Adding elements](#adding-elements)
* [Get a value of one key using [ ] Square-bracket.](#get-a-value-of-one-key-using---square-bracket)
* [Accessing a key that does not exist](#accessing-a-key-that-does-not-exist)
* [Alternative-to “throwing-an error” if-a key-does not-exist by using .get() method to access the dict](#alternative-to-throwing-an-error-if-a-key-does-not-exist-by-using-get-method-to-access-the-dict)
* [Sometimes you want to return None or a default value if key does not exist](#sometimes-you-want-to-return-none-or-a-default-value-if-key-does-not-exist)
* [Adding-a new-entry to-dictionary](#adding-a-new-entry-to-dictionary)
* [Changing/updating values via key access](#changingupdating-values-via-key-access)
* [Changing/updating-values via .update() method](#changingupdating-values-via-update-method)
* [Deleting a specific key and its value](#deleting-a-specific-key-and-its-value)
   * [Option 1 - del keyword](#option-1---del-keyword)
   * [Option 2 - .pop() method](#option-2---pop-method)
* [Finding-out the-number of-keys in-dict with-len() function](#finding-out-the-number-of-keys-in-dict-with-len-function)
* [How-to loop-through all-the keys-and values](#how-to-loop-through-all-the-keys-and-values)
   * [Print-all keys-with .keys() method](#print-all-keys-with-keys-method)
   * [Print-all values-with .values() method](#print-all-values-with-values-method)
   * [Print-both keys-and values-with .items() method](#print-both-keys-and-values-with-items-method)
   * [Looping-is slightly-different then-lists because-dicts are-concerned with-pairs (Key : Value)](#looping-is-slightly-different-then-lists-because-dicts-are-concerned-with-pairs-key--value)
   * [How to loop through keys AND values](#how-to-loop-through-keys-and-values)

* [Test Your Understanding](#Test-Your-Understanding)

# Terminology

Dictionaries are collections of key-value pairs. The *Keys* are unique. Dictionaries are useful when we want to access list of items that are related by a piece of data; the *key* in this case.

Dictionaries are also called associative arrays, maps, and tables. Usually they are implemented using hashing to achieve the fastest performance.

# Key/Value pairs definition
A key-value pair contains two parts:
- keyword that identify a set of associated values.
- and value associated with that key.

In fact, the naming dictionary is taken from the physical dictionary in which we look up for a  word's definition.
A word in this physical dictionary is the *key*. And the definition is the *value*.   


Let us go ahead with some dictionary example to represent a car:
# { }, Dict notation, curly braces
We use curly braces to declare dictionaries:
```
a_car_dict = {};
```

# Adding elements
Now within the curly braces you may add the key and separated it from the value using a colon: `:` like this:
```
a_car_dict = {
  "brand": "Ford"
};
```

we can add more key-value pairs by separating them using commas:
```
a_car_dict = {
    'brand': 'Ford',
    'Model': 'Explorer',
    'Year': '2012',
    'Colors': ['black', 'white', 'red']
}

print(a_car_dict)
```
Output:
```
{'brand': 'Ford', 'Model': 'Explorer', 'Year': '2012', 'Colors': ['black', 'white', 'red']}
Process finished with exit code 0
```

# Get a value of one key using `[ ]` Square-bracket.
We can access the dictionary using square-bracket:
```
a_car_dict = {
    'Brand': 'Ford',
    'Model': 'Explorer',
    'Year': '2012',
    'Colors': ['black', 'white', 'red']
}

print(a_car_dict['Colors'])
```
Output:
```
['black', 'white', 'red']
```

# Accessing a key that does not exist
For example, if you try to accessing a key that does not exists like `Engine`
```
print(a_car_dict['Engine'])
```
, you will get `Key Error` because `Engine` does not exist.

Output:
```
C:\Users\rousa\PycharmProjects\pythonProject1\venv\Scripts\python.exe C:/Users/rousa/PycharmProjects/pythonProject1/main.py
Traceback (most recent call last):
  File "C:/Users/rousa/PycharmProjects/pythonProject1/main.py", line 26, in <module>
    print(a_car_dict['Engine'])
KeyError: 'Engine'


Process finished with exit code 1

```

# Alternative-to “throwing-an error” if-a key-does not-exist by using `.get()` method to access the dict
Throwing an error might not be the ideal action for non existential keys. If you want to return a `None` instead, you may use the dictionary `get()` method.
```
print(a_car_dict.get('Engine'))
print(a_car_dict.get('Brand'))
```
Output:
```
None
Ford
```


# Sometimes you want to return `None` or a default value if key does not exist
We can also specify a default value for the keys that do not exist by passing it as a second argument to the `get` method:
```
print(a_car_dict.get('Engine size', 'not found'))
```
Output:
```
not found
```


# Adding-a new-entry to-dictionary
Let us try to add the key, `Engine`, that did not exist:
```
a_car_dict = {    
  'Brand': 'Ford',
  'Model': 'Explorer',
  'Year': '2012',
  'Colors': ['black', 'white', 'red']
}
a_car_dict['Engine'] = '2.3'

print(a_car_dict.get('Engine', 'not found'))
```

Output:
```
2.3
```


# Changing/updating values via key access
If the key already exists, we can update it by setting the value:
```
a_car_dict = {    'Brand': 'Ford',     'Model': 'Explorer','Year': '2012',     'Colors': ['black', 'white', 'red']
}
a_car_dict['Year'] = '2013'


print(a_car_dict)
```
Output:
```
{'Brand': 'Ford', 'Model': 'Explorer', 'Year': '2013', 'Colors': ['black', 'white', 'red'], 'Engine': '2.3'}
```

# Changing/updating-values via .update() method
We can use the `update` method to update multiple keys at the same time:
```
a_car_dict = {
    'Brand': 'Ford',
    'Model': 'Explorer',
    'Year': '2012',
    'Colors': ['black', 'white', 'red']
}
# a_car_dict['Engine'] = '2.3'
# a_car_dict['Year'] = '2013'
a_car_dict.update({'Year':'2013', 'Engine': '2.3' })
print(a_car_dict)
```
Output:
```
{'Brand': 'Ford', 'Model': 'Explorer', 'Year': '2013', 'Colors': ['black', 'white', 'red'], 'Engine': '2.3'}

```


# Deleting a specific key and its value
## Option 1 - `del` keyword
```
a_car_dict = {
    'Brand': 'Ford',
    'Model': 'Explorer',
    'Year': '2012',
    'Colors': ['black', 'white', 'red']
}

del a_car_dict['Year']

print(a_car_dict)
```
Output:
```
{'Brand': 'Ford', 'Model': 'Explorer', 'Colors': ['black', 'white', 'red']}

```
## Option 2 - `.pop()` method
```
a_car_dict = {
    'Brand': 'Ford',
    'Model': 'Explorer',
    'Year': '2012',
    'Colors': ['black', 'white', 'red']
}

year = a_car_dict.pop('Year')

print(a_car_dict)
print(year)
```
Output:
```
{'Brand': 'Ford', 'Model': 'Explorer', 'Colors': ['black', 'white', 'red']}
2012
```
Remember that the `.pop()` method not only removes the item but returns it to you]

# Finding-out the-number of-keys in-dict with-len() function
```
a_car_dict = {
    'Brand': 'Ford',
    'Model': 'Explorer',
    'Year': '2012',
    'Colors': ['black', 'white', 'red']
}

print(len(a_car_dict))
```
Output:
```
4
```


# How-to loop-through all-the keys-and values
## Print-all keys-with `.keys()` method
```
a_car_dict = {
    'Brand': 'Ford',
    'Model': 'Explorer',
    'Year': '2012',
    'Colors': ['black', 'white', 'red']
}

print(a_car_dict.keys())
```
Output:
```
dict_keys(['Brand', 'Model', 'Year', 'Colors'])
```

## Print-all values-with `.values()` method
```
a_car_dict = {
    'Brand': 'Ford',
    'Model': 'Explorer',
    'Year': '2012',
    'Colors': ['black', 'white', 'red']
}

print(a_car_dict.values())

```
Output:
```
dict_values(['Ford', 'Explorer', '2012', ['black', 'white', 'red']])
```
## Print-both keys-and values-with `.items()` method
```
a_car_dict = {
    'Brand': 'Ford',
    'Model': 'Explorer',
    'Year': '2012',
    'Colors': ['black', 'white', 'red']
}

print(a_car_dict.items())

```
Output:
```
dict_items([('Brand', 'Ford'), ('Model', 'Explorer'), ('Year', '2012'), ('Colors', ['black', 'white', 'red'])])
```
## Looping-is slightly-different then-lists because-dicts are-concerned with-pairs (Key : Value)
```
a_car_dict = {
    'Brand': 'Ford',
    'Model': 'Explorer',
    'Year': '2012',
    'Colors': ['black', 'white', 'red']
}
for key in a_car_dict.keys():
    print(key)


```
Output:
```
Brand
Model
Year
Colors

```
## How to loop through keys AND values
```
a_car_dict = {
    'Brand': 'Ford',
    'Model': 'Explorer',
    'Year': '2012',
    'Colors': ['black', 'white', 'red']
}
for key, value in a_car_dict.items():
    print(key, ":", value)


```
Output:
```
Brand :  Ford
Model :  Explorer
Year :  2012
Colors :  ['black', 'white', 'red']
```

# Test Your understanding
Which of the following are true of Python dictionaries:
- A dictionary can contain any object type except another dictionary.
- Dictionaries can be nested to any depth.
- Items are accessed by their position in a dictionary.
- All the keys in a dictionary must be of the same type.
- Dictionaries are accessed by key.


<details><summary>Answer</summary>
True statements:
- Dictionaries can be nested to any depth.
- Dictionaries are accessed by key.


Explanation:
Python dictionaries are similar to lists in that they are mutable and can be nested to any arbitrary depth (constrained only by available memory).

A dictionary can contain any type of Python object, including another dictionary. The keys in a given dictionary do not need to be the same type as one another, nor do the values.

Dictionary elements are accessed by key. Unlike with list indexing, the order of the items in a dictionary plays no role in how the items are accessed.

Even though dictionary access does not rely on item order, as of version 3.7 the Python language specification does guarantee that the order of items in a dictionary is maintained once the dictionary is created.
[Source] (https://realpython.com/quizzes/python-dicts/viewer/)
</details

# Sources & References
[1](https://www.youtube.com/watch?v=XCcpzWs-CI4&ab_channel=Socratica)
[2](https://docs.python.org/3/tutorial/datastructures.html#tuples-and-sequences)
[3](https://www.tutorialspoint.com/List-vs-tuple-vs-dictionary-in-Python)
[4](https://realpython.com/python-dicts/)
[5](https://www.w3schools.com/python/python_dictionaries.asp)
[6](https://www.youtube.com/watch?v=daefaLgNkw0&ab_channel=CoreySchafer)
