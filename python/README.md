### Python CheatSheet

Python iterables will return True if the are not emtpy and false if they are emtpy

```python 
li = ['a','b','c']

if li: # is not emtpy
    # do something
elif not li: # it is empty
    # do something else
```

Check a type

```python
i = 1
type(i) is int # True
isinstance(i, int) # Will test if it is that type or any subtype
```

Define Infinity

```python
float('inf') # -> inf
-float('inf') # -> -inf

```

#### List (Stack and Queue)

```python 
li = ['a','b','c'], li = list("abc")

# check list equality
[1,2,3] == [1,2,3] # -> True

# pre alloc a buffer with some default value
[-1] * 3 # -> [-1, -1, -1]
[1,2] * 2 # -> [1, 2, 1, 2] scalar repeats the pattern n times
```


| Function       | Result | Notes|
| ------------- |-------------|-------------| 
| `enumerate(li)`| `[(1,'a'), (1,'b'), (3,'c')]` | 
| `zip([1,2,3], ['a','b','c'])`| `[(1,'a'), (1,'b'), (3,'c')]` | 
| `[3,1,2].sort()`| `[1,2,3]` | mutates original
| `def cmp(a, b) [3,1,2].sort(cmp)`| `[1,2,3]` | define a compare func that tells it how to sort `return (1 or 0 or -1)`
| `[1,2] + [3,2]`| `[1,2,3,2]` | 
| `1 in [1,2,3]`| `True` | 
| `[3,1,2].pop()`| `[1,2]` | removes back and returns the value
| `[1,2,3].pop(0)`| `[2,3]` | removes front and returns the value
| `[1,2,3].insert(0,4)`| `[4,1,2,3]` | insert front
| `[1,2,3].append(4)`| `[1,2,3,4]` | push back

#### Slices

Start is inclusive and end is exclusive. Start and end use zero based indexing.
Slices return a copy

```python
[start:end:skip] 
li = [1,2,3,4]
```

| Function       | Result | Notes|
| ------------- |-------------|-------------| 
| `li[0:1]`| `[1]` | 
| `li[0:2]`| `[1,2]` | 
| `li[:2]`| `[1,2]` | you can omit the start if you want to start from the begining
| `li[2:]`| `[3,4]` | same thing with the end (don't forget start and end are inclusive, exclusive respectivley
| `li[2:4]`| `[3,4]` | 
| `li[0:4:2] or [::2]`| `[1,3]` | grab a copy of the whole array and return every 2nd index starting at 0
| `li[-1]`| `[4]` | the last element 



#### Dictionary

```python 
d = dict(a=1, b=2, c=3) or d = {'a':1, 'b':2, 'c':3 } or d = dict([(a,1), (b,2), (c,3)])
```

| Function       | Result | Notes|
| ------------- |-------------|-------------| 
| `d.keys()`| `[a,b,c]` | 
| `d.values()`| `[1,2,3]` | 
| `d.items()`| `[(a,1), (b,2), (c,3)]` | 
| `d.update({'e':5, 'a':7})`| ` {'a':7, 'b':2, 'c':3, 'e:5 }` | This provides a really nice way of merging two dicts
| `d['a']`| `1` | 
| `d['d'] = 4`| ` {'a':1, 'b':2, 'c':3, 'd:4' }` | 
| `d.pop('c')`| ` {'a':1, 'b':2}` | Throws exception if not found
| `'a' in d`| `True` | 

#### Set

```python 
s = set("abcd"), set = set([1,2,3]), s = {1,2,3}
```

| Function       | Result | Notes|
| ------------- |-------------|-------------| 
| `set([1,2,3]) - set([1,2])`| `{3}` | difference
| `set([1,2,3]) pipe set([1,2,4])`| `{1,2,3,4}` | union
| `set([1,2,3]) & set([1,2,4])`| `{1,2}` | intersection
| `set([1,2,3]).add(4)`| `{1,2,3,4}` | 
| `set([1,2,3]).remove(1)`| `{2,3}` | throw error if not found
| `1 in set([1,2,3])`| `True` | 


#### Matrix

```python
mat = [
     [1, 2, 3, 4],
     [5, 6, 7, 8],
     [9, 10, 11, 12],
 ]
```

#### Strings

``` python 

txt = "hello, my name is Peter, I am 26 years old"
x = txt.split(", ")

"".join(x) # will merge back into a single string

```

#### Closures

``` python
def parent():
    a = 1
    b = []
    def child():
        nonlocal a # must redeclare pointers as nonlocal when using them within a closure if trying to modify
        # a is Ok if using at as a read only variable
        a += 1 # parent a is now 2
        b.append(a) # OK to modify parent since we aren't chaning the value of b
```

#### Utils

