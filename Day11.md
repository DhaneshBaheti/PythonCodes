```python
Y = [2*x+3 for x in range (2,8)]
print(Y)
```

    [7, 9, 11, 13, 15, 17]
    


```python
Y=[2*x+3 for x in range (2,8) if x%3!=0]
print(Y)
```

    [7, 11, 13, 17]
    


```python
Y=[[x,y] for x in range(5) for y in range (x,5) if x+y==5]
print(Y)
```

    [[1, 4], [2, 3]]
    


```python
Y=[[x,y,z] for x in range(5) for y in range(x,5) for z in range(10) if x+y==z]
print(Y)
```

    [[0, 0, 0], [0, 1, 1], [0, 2, 2], [0, 3, 3], [0, 4, 4], [1, 1, 2], [1, 2, 3], [1, 3, 4], [1, 4, 5], [2, 2, 4], [2, 3, 5], [2, 4, 6], [3, 3, 6], [3, 4, 7], [4, 4, 8]]
    


```python
S=['Rahul','Neha','Preethi','Gokul']
Y=[len(i) for i in S]
print(Y)
```

    [5, 4, 7, 5]
    


```python
S=['cash','cache','pistol','pauper']
Y=[i for i in S if i[0] not in i[1:]]
print(Y)
```

    ['cash', 'pistol']
    


```python
S=['cash','cache','pistol','pauper']
Y=[i for i in S if i.count(i[0])==1]
print(Y)
```

    ['cash', 'pistol']
    


```python
S=['cash','cache','pistol','pauper']
Y=[i for i in S if i[0] in i[1:]]
print(Y)
```

    ['cache', 'pauper']
    


```python
S=['cash','cache','pistol','pauper']
Y=[i for i in S if i.count(i[0])>1]
print(Y)
```

    ['cache', 'pauper']
    


```python
N=[i for i in range(100) if i%7==0 and i%3!=0]
print(N)
```

    [7, 14, 28, 35, 49, 56, 70, 77, 91, 98]
    


```python
N=[i for i in range(10000,10100) if all (i%j!=0 for j in range(2,int(i**0.5+1)))]
print(N)
```

    [10007, 10009, 10037, 10039, 10061, 10067, 10069, 10079, 10091, 10093, 10099]
    


```python
N=[i for i in range(2,20) if any(i%j==0 for j in range(2,i))]
print(N)
```

    [4, 6, 8, 9, 10, 12, 14, 15, 16, 18]
    


```python
S=['Mary','George','Anna','Peter']
Y=[i for i in S if all(i[j]!='a' for j in range(len(i)))]
print(Y)
```

    ['George', 'Peter']
    


```python
S=['Mary','George','Anna','Peter']
Y=[i for i in S if any(i[j]=='a' for j in range(len(i)))]
print(Y)
```

    ['Mary', 'Anna']
    


```python
def perm(s):
    if len(s)==1:
        return[s] #Base Case : an empty string has only one permutation (itself)
    else:
        # for each char in s, generate permutation of the rest of string
        return [i+p for i in s for p in perm(s.replace(i,''))]
#Example Usage
mystr='pqr'
print(perm(mystr))
```

    ['pqr', 'prq', 'qpr', 'qrp', 'rpq', 'rqp']
    


```python
S=['Rahul','Neha','Preethi','Gokul']
vowel=[sum (1 for char in word if char.lower() in 'aeiou') for word in S]
print(vowel)
```

    [2, 2, 3, 2]
    


```python
S=['Rahul','Neha','Preethi','Gokul']
consonant=[sum (1 for char in word if char.lower() not in 'aeiou') for word in S]
print(consonant)
```

    [3, 2, 4, 3]
    


```python
matrix = [[1,2,3],[4,5,6],[7,8,9]]
odd=[element for row in matrix for element in row if element%2!=0]
print(odd)
```

    [1, 3, 5, 7, 9]
    


```python
matrix = [[1,2,3],[4,5,6],[7,8,9]]
even=[element for row in matrix for element in row if element%2==0]
print(even)
```

    [2, 4, 6, 8]
    


```python
matrix=[[j for j in range(5)] for i in range(5)]
print(matrix)
```

    [[0, 1, 2, 3, 4], [0, 1, 2, 3, 4], [0, 1, 2, 3, 4], [0, 1, 2, 3, 4], [0, 1, 2, 3, 4]]
    


```python
list(zip([1,2,3,4,5],[5,6,7,8,9,10]))
```




    [(1, 5), (2, 6), (3, 7), (4, 8), (5, 9)]




```python
y = [[1,2,3,4,5],[5,6,7,8,9,10]]
print(list(zip(*y)))
```

    [(1, 5), (2, 6), (3, 7), (4, 8), (5, 9)]
    


```python
x = [[12,7,3],[4,5,6],[7,8,9]]
y = [[5,8,1,2],[6,7,3,0],[4,5,9,1]]
#result = [[0]*len(y[0]) for _ in range(len(x))]
result = [
    [sum(a*b for a,b in zip(xrow,ycol)) for ycol in zip(*y)]for xrow in x
]
print(result)
```

    [[114, 160, 60, 27], [74, 97, 73, 14], [119, 157, 112, 23]]
    


```python

```
