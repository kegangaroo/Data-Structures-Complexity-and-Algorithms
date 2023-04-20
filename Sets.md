# Sets
- An Unordered collection without repitition
- mathematical way to describe collection of different unique objects
- Sets membership operation is one of the fastest operations compared to other python data types
- Sets are mutable and have many methods and operations that can mutate the data

## Define a Set
```python
# Set definition examples:
example_set1 = {1, 2, 3}
example_set2 = {'h','e','l','l','o'}

print('example_set1:', example_set1)
print('example_set2:', example_set2) # Notice there is only 1 'l'; Also notice the order of the values outputted
print('--')

singleton_set = {7}
empty_set = set() # this is because {} is reversed for a different feature in python 3.

print('Singleton:', singleton_set)
print('Empty Set:', empty_set)
```
***Output:***
example_set1: {1, 2, 3}
example_set2: {'o', 'e', 'h', 'l'}

Singleton: {7}
Empty Set: set()
--
### Basic Built-in Functions
```python
# Basic Built-in Functions w/ Sets

example_set = set('hello') # set() turns an iterable into a set
print('example_set:', example_set)
print('--')

print('Number of Values:', len(example_set)) # length function
print('Minimum Value:', min(example_set)) # min function
print('Maximum Value:', max(example_set)) # max function
print('--')

# tuple to set
tup = (2,3,5,7)
print('tup to set:', set(tup))

# list to set
array = ['orange']*2 +  ['watermelon', 'apple'] + ['kiwi'] * 10
print('Original Array:', array)
print('list to set:', set(array))
```
***Output:***
example_set: {'o', 'e', 'h', 'l'}

Number of Values: 4
Minimum Value: e
Maximum Value: o

tup to set: {2, 3, 5, 7}
Original Array: ['orange', 'orange', 'watermelon', 'apple', 'kiwi', 'kiwi', 'kiwi', 'kiwi', 'kiwi', 'kiwi', 'kiwi', 'kiwi', 'kiwi', 'kiwi']
list to set: {'watermelon', 'orange', 'apple', 'kiwi'}
--
### Membership
```python
# Membership Example
example_set = set('hello')

print("Membership of: \'h\'", 'h' in example_set)
print("Non-Membership of: \'z\'", 'z' not in example_set)
```
***Output:***
Membership of: 'h' True
Non-Membership of: 'z' True

### Accessing Values
```python
# Iteration of a Set
example_set = {2,3,5,7,11,13}

for v in example_set:
    print('Values of example_set:', v)
```
***Output:***
Values of example_set: 2
Values of example_set: 3
Values of example_set: 5
Values of example_set: 7
Values of example_set: 11
Values of example_set: 13

### Adding and Removing Values
```python
# Adding and Removing Values
languages = set() # empty set initialization

programming_languages = ['C', 'C#', 'Java', 'Python', 'HTML', 'CSS', 'JavaScript', 'Haskell']

for item in programming_languages:
    languages.add(item) # .add() method adds an item to a set

print('Languages set:', languages)
print('--')

languages.discard('HTML') # looks for the target value, if found, it will remove from the set
print('HTML deleted:', languages)

languages.remove('CSS') # remove can be used to delete a value;
# only difference is it will raise an error if the target is not found
print('CSS deleted:', languages)

random_remove = languages.pop() # .pop() method deletes a random value and return the value ... not recommended
print('Randomly Removed value:', random_remove)

languages.clear() # .clear() will empty out a set : output is set()
print('Empty languages:', languages)
```
***Output:***
Languages set: {'HTML', 'CSS', 'JavaScript', 'Python', 'Haskell', 'Java', 'C', 'C#'}
--
HTML deleted: {'CSS', 'JavaScript', 'Python', 'Haskell', 'Java', 'C', 'C#'}
CSS deleted: {'JavaScript', 'Python', 'Haskell', 'Java', 'C', 'C#'}
Randomly Removed value: JavaScript
Empty languages: set()
--
## Set Operators

- Union - The joining/combining of two sets
```python
# Union Example:
set1 = set('hello')
set2 = set('world')

result = set1 | set2 # | is the union operator ... all the members of both set are combined to a single set
# Recall that: there are no duplicates
print('set1 union set 2:', result)
```
- Intersection - Members/Items that only exists in both sets
```python
# Union Example:
set1 = set('hello')
set2 = set('world')

result = set1 & set2 # & is the intersection operator
print('Intersection of set1 and set2:', result)
```
- Difference - Members/items that only exists in the first set and not the second set
```python
# Difference Example:
set1 = set('hello')
set2 = set('world')

result1 = set1 - set2 # - is the difference operator ... this is set1 difference set2
result2 = set2 - set1 # set2 difference set1

print('set1 - set2:', result1)
print('set2 - set1:', result2)
```
- Symmetric Difference - Members/items that exists one or the other set, but not both sets
```python
# Symmetric Difference Example:
set1 = set('hello')
set2 = set('world')

result = set1 ^ set2 # ^ is the symmetric difference operator

print('Symmetric Difference of:', result)
```
- Proper Subset - This is a boolean operator. A is proper subset of B if all members of A is found in B, but A cannot be exactly the same as B
```python
# Proper Subset Example:
set1 = {1,2,3}
set2 = {1,2,3,4}
set3 = {1,2,3}
set4 = set('hello')

print('Is set1 proper subset of set2?:', set1 < set2) # < is the proper subset operator
print('Is set1 proper subset of set3?:', set1 < set3)
print('Is set1 proper subset of set4?:', set1 < set4)
```
- Subset - A is a Proper Subset of B if A < B is True, but A can equal to B unlike a proper subset
```python
# Subset Example:
set1 = {1,2,3}
set2 = {1,2,3,4}
set3 = {1,2,3}
set4 = set('hello')

print('Is set1 a subset of set2?:', set1 <= set2) # <= is the subset operator
print('Is set1 a subset of set3?:', set1 <= set3) # Notice the difference in value here
print('Is set1 a subset of set4?:', set1 <= set4)
```
- Proper Superset - A is a proper superset of B if A has all the values of B and more, but they are not equal to each other
```python
# Superset Example:
set1 = {1,2,3,4}
set2 = {1,2,3,4}
set3 = {1,2,3}
set4 = set('hello')

print('Is set1 proper superset of set2?:', set1 > set2) # > is the proper superset operator
print('Is set1 proper superset of set3?:', set1 > set3)
print('Is set1 proper superset of set4?:', set1 > set4)
```
- Superset - A is a superset of B if A > B or A == B
```python
# Superset Example:
set1 = {1,2,3,4}
set2 = {1,2,3,4}
set3 = {1,2,3}
set4 = set('hello')

print('Is set1 superset of set2?:', set1 >= set2) # >= is the proper superset operator
print('Is set1 superset of set3?:', set1 >= set3)
print('Is set1 superset of set4?:', set1 >= set4)
```
- Disjoint - Two set are consided disjointed when two sets share no common value
```python
# Disjoint Example
# .isdisjoint() is a set method to check for such property between two sets.

set1 = {1,2,3,4}
set2 = {5,6,7}
set3 = {1,2,3,4,5}

print('set1 intersect set2:', set1 & set2) # Output is an empty set
print('set1 intersect set3:', set1 & set3) # Output is an non-empty set
print('--')
print('set 1 disjoint set 2 check:', set1.isdisjoint(set2)) # Therefore .isdisjoint() evaluates to True
print('set 1 disjoint set 3 check:', set2.isdisjoint(set3))
```
--
### Assignment Operation & Updating Methods
This is a way to affect an original set with another and assign the result back to the original set
```python
# Union and Update --> Update the set, adding elements from all others.
a = set('abracadabra')
b = set('alacazam')

a |= b # same as: a.update(b)
print('Union Update:', a)

# Intersection and Update --> Update the set, keeping only elements found in it and all others.
a = set('abracadabra')
b = set('alacazam')

a &= b # same as: a.intersection_update(b)
print('Intersection Update:', a)

# Difference and Update --> Update the set, removing elements found in others.
a = set('abracadabra')
b = set('alacazam')

a -= b # same as: a.difference_update(b)
print('Difference Update:', a)

# Symmetric Difference and Update --> Update the set, keeping only elements found in either set, but not in both.
a = set('abracadabra')
b = set('alacazam')

a ^= b # same as: a.symmetric_difference_update(b)
print('Symmeteric Difference Update:', a)
```
***Output:***
Union Update: {'b', 'a', 'z', 'r', 'l', 'm', 'd', 'c'}
Intersection Update: {'c', 'a'}
Difference Update: {'b', 'r', 'd'}
Symmeteric Difference Update: {'b', 'z', 'r', 'l', 'm', 'd'}

### Set Comprehension
Much like list comprehension, sets support comprehension as well
```python
# Set Comprehension Example
def isPalindrome(x):
    ''' isPalindrome() returns True if string X is a palindrome '''
    return x == x[::-1]

nums = list(range(1,10000))
palindromic_set = {num for num in nums if isPalindrome(str(num))}

print('Palindromic Numbers Set from 1 to 10000:')
print(palindromic_set)
```
***Output:***
Palindromic Numbers Set from 1 to 10000
