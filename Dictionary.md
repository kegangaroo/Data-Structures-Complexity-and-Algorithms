# Dictionary
## Operations
- Adding a pair
- Removing a pair
- Modifying a pair
- Lookup of a value associated with a particular key

### What is a dictionary? 
A Dictionary is a way to store data by using a key and value method, assigning them to each other to make recall efficient and retain values for later use
A dictionary uses squiggly bracets to define whats inside, and uses a full colin to seperate the key and value assigned together

### Defining  Dictionary
```python
# Dictionary Example
sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

# There are 3 items: each with their unique addresses and value
# Accessing
print('Sammy dict:', sammy)
print('Username:', sammy['username'])
print('Online Status:', sammy['online'])
print('Follower Count:', sammy['followers'])
```
***Output:***
-
Sammy dict: {'username': 'sammy', 'online': True, 'followers': 42}
Username: sammy
Online Status: True
Follower Count: 42

### Keys
Keys must be immutabel, are a specific location to the assigned value, two keys of identical names cannot exist, and the newest one will superceed the older one

### Values
Values within a key may be anything (specifically any data type)

### Dictionary Updates
Additions and modifications cann be made stating the key, and the new value inside to either create a new key, or override the value already in place
 
### EXAMPLE
```python
# Update Example

sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

sammy['followers'] += 10 # We are adding 10 to the value located at key: 'followers'
sammy['verified'] = True # We added a new value at a new key: 'verified'
sammy['username'] = 'SammySammy'

print('Sammy Dict:', sammy)
```
***Output:***
-
Sammy Dict: {'username': 'SammySammy', 'online': True, 'followers': 52, 'verified': True}

### Dictionary Deletions
We can delete keys from the dictionary therefore deleting the value it held along with it, or, using a specific as shown below, you can clear the entire dictionary

### EXAMPLE
```python
# Deletion Example

sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

del sammy['followers'] # del is a keyword used to help us to execute a removal
print('followers key deleted:', sammy)

sammy.clear() # {} is considered an empty dict
print('emptying out a dictionary', sammy)
print('--\n\n')

del sammy
print('Deleting sammy, should create an error when referenced again', sammy)
```
***Output:***
-
followers key deleted: {'username': 'sammy', 'online': True}
emptying out a dictionary {}
NameError: name 'sammy' is not defined

### Membership & Built-in Functions
The operators **in** and **not in** exist to use on the key in a dictionary

**Built-in Functions include:**
- Len()
- Max()
- Min()
- Str()
- List()

- .copy(), will copy a dictionary, key and values
- fromkeys(), will only copy the keys from a dictionary, and not the values it held previously

### Methods and Iteration
**Methods include:**
- A.keys() –> Returns a sequence of keys/addresses in A
- A.values() –> Returns a sequence of item values in A
- A.items() –> Returns a sequence of key,item pairs in A
- A.get(address) –> Returns the item value at address
- A.update(B) –> Extends A with the dictionary of key,value pairs of B

**Iteration**
There are 3 ways to iterate through a dictionary
- Iterating the keys
- Iterating the values
- Iterating both the key and value pairs by **unpacking**

### Specialities
Dictionaries support comprehension
You must specify where the keys and the values are

**EXAMPLE**
```python
# dict() Example

example_data = [
    ('one', 3),
    ('two', 3),
    ('three', 5)
]

data_dict = dict(example_data)
print('data_dict:', data_dict)
print('--')

# Dictionary Comprehension
# Goal: Take string numerals and assign them with their integer square
# - keys : string numerals
# - values: integer squares

example_data2 = ['1', '2', '3', '4', '5']

data2_dict = {x : int(x)**2 for x in example_data2}

print('data2_dict:', data2_dict)
```
***Output:***
-
data_dict: {'one': 3, 'two': 3, 'three': 5}
data2_dict: {'1': 1, '2': 4, '3': 9, '4': 16, '5': 25}
