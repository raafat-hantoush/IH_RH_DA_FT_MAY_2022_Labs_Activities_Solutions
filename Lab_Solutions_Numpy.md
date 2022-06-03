


# 100 numpy exercises

This is a collection of exercises that have been collected in the numpy mailing list, on stack overflow
and in the numpy documentation. The goal of this collection is to offer a quick reference for both old
and new users but also to provide a set of exercises for those who teach.


If you find an error or think you've a better way to solve some of them, feel
free to open an issue at <https://github.com/rougier/numpy-100>.
File automatically generated. See the documentation to update questions/answers/hints programmatically.

#### 1. Import the numpy package under the name `np` (★☆☆)


```python
import numpy as np
```

#### 2. Create a null vector of size 10 (★☆☆)


```python
Z = np.zeros(10)
print(Z)
```


#### 3. Create a null vector of size 10 but the fifth value which is 1 (★☆☆)

```python
Z = np.zeros(10)
Z[4] = 1
print(Z)
```
#### 4. Create a vector with values ranging from 10 to 49 (★☆☆)


```python
Z = np.arange(10,50)
print(Z)
```

#### 5. Create a 3x3 matrix with values ranging from 0 to 8 (★☆☆)


```python
Z = np.arange(9).reshape(3, 3)
print(Z)
```
#### 6. Find indices of non-zero elements from [1,2,0,0,4,0] (★☆☆)


```python
nz = np.nonzero([1,2,0,0,4,0])
print(nz)
```
#### 7. Create a 3x3 identity matrix (★☆☆)


```python
Z = np.eye(3)
print(Z)
```
#### 8. Create a 3x3x3 array with random values (★☆☆)


```python
Z = np.random.random((3,3,3))
print(Z)
```
#### 9. Create a 10x10 array with random values and find the minimum and maximum values (★☆☆)


```python
Z = np.random.random((10,10))
Zmin, Zmax = Z.min(), Z.max()
print(Zmin, Zmax)
```
#### 10. Create a random vector of size 30 and find the mean value (★☆☆)


```python
Z = np.random.random(30)
m = Z.mean()
print(m)
```

#### 11. Create a 5x5 matrix with values 1,2,3,4 just below the diagonal (★☆☆)


```python
Z = np.diag(1+np.arange(4),k=-1)
print(Z)
```
#### 12. Normalize a 5x5 random matrix (★☆☆)


```python
Z = np.random.random((5,5))
Z = (Z - np.mean (Z)) / (np.std (Z))
print(Z)
```


#### 13. How to find common values between two arrays? (★☆☆)


```python
Z1 = np.random.randint(0,10,10)
Z2 = np.random.randint(0,10,10)
print(np.intersect1d(Z1,Z2))
```
#### 14. Create a random vector of size 10 and sort it (★★☆)


```python
Z = np.random.random(10)
Z.sort()
print(Z)
```

#### 15. Create random vector of size 10 and replace the maximum value by 0 (★★☆)

```python
Z = np.random.random(10)
Z[Z.argmax()] = 0
print(Z)
```

#### 16. Subtract the mean of each row of a matrix (★★☆)


```python
# Author: Warren Weckesser

X = np.random.rand(5, 10)

# Recent versions of numpy
Y = X - X.mean(axis=1, keepdims=True)

# Older versions of numpy
Y = X - X.mean(axis=1).reshape(-1, 1)

print(Y)
```
#### 17. How to get the n largest values of an array (★★★)


```python
Z = np.arange(10000)
np.random.shuffle(Z)
n = 5

# Slow
print (Z[np.argsort(Z)[-n:]])

# Fast
print (Z[np.argpartition(-Z,n)[:n]])
```
#### 18. Create a random 5*3 matrix and replace items that are larger than 4 by their squares ( Example: 6 --> 36)
```python
Z = np.random.random((5,5))
np.where(Z>0.1,Z**2,Z)
```