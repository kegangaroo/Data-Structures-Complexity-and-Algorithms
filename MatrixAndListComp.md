# Data-Structures-Complexity-and-Algorithms

## Matrices and List Comprehension

### What is a Matrix
- although python has no matrix funtion within it, a matrix is a data structure comprised of rows and coloumns
- All rows must have the same number of values
- All columns must have the same number of values
- All items in the 2D List must have the same data types
- Since indexing always starts at 0, row 1 is located at matrix_A[0]

### Example of Matrix
```python
# Python 3 Representation of matrix A

matrix_A = [
    [1, 2, 3, 4],
    [5, 6, 7, 8]
]

# Accessing Matrix A
print('Row 1: %s' % matrix_A[0]) # Recall: Indexing starts at zero in Python
print('Value at Row 2 Column 2: %s' % matrix_A[1][1])
```

## List Comprehension

### What is List Comprehension
List Comprehension is used when . . .
- The list is a result of some operations applied to all its items
- It is a made from another sequence/iterable data
- The list is member of another list/sequence/iterable data that satisfies a certain condition

### How does it work
- A Square Bracket containing an expression that describes the list
- One or more For clause to explain its members
- Then a zero or more if clauses depending on the complexity of the list

### Example 1
``` python
# Old Method
squares = []
for i in range(10):
    squares.append(i ** 2)

print('Our result: %s' % squares)

# List Comprehension

squares = [i**2 for i in range(10)]

print('Our new result: %s' % squares)
```

### Example 2
Create the list: [[1, 3], [1, 4], [2, 3], [2, 1], [2, 4], [3, 1], [3, 4]]
From
A = [1,2,3]
B = [3,1,4]

By using list comprehension
``` python
# Solution
a = [1,2,3]
b = [3,1,4]

result = [[x, y] for x in a for y in b if x != y]
print(result)
```

### Example 3
Use list comprehension to turn a 2D array called vec to a single list

vec = [[1,2,3], [4,5,6], [7,8,9]]
Output: [1, 2, 3, 4, 5, 6, 7, 8, 9]
``` python
# Solution

vec = [[1,2,3], [4,5,6], [7,8,9]]

result = [value for row in vec for value in row]
print('Vec as a single list of values: %s' % result)
```







