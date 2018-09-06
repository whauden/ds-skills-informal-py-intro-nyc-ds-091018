
# Python as a calculator

One of the simplest things you can do with python is begin to use it as a calculator as so:


```python
3+3
```




    6



You can use all the standard operators:
* $+$ (add)
* $-$ (subtract
* $*$ (multiply)
* $/$ (divide)
* $**$ (raise to an exponent)
* $\%$ (remainder; modular arithmetic)
* $//$ (quotient; floor division)


```python
5-2
```




    3




```python
5+2
```




    7




```python
5*2
```




    10




```python
5/2
```




    2.5




```python
5**2
```




    25




```python
5%2 #Remainder/modular arithmetic
```




    1




```python
5//2 #Quotient/floor division
```




    2



# Naming things with Variables
We can use the `=` sign to assign values to a variable.


```python
width = 5
```


```python
width
```




    5




```python
height = 4
```


```python
width * height
```




    20



If a variable is not defined, you wil get an error


```python
depth
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-14-15a3e886aba1> in <module>()
    ----> 1 depth
    

    NameError: name 'depth' is not defined


# Strings
Strings are python's built in data type for storing text. Keep in mind, that digits can also be stored as strings, but will behave differently when stored as strings rather then *float* or *integer* numbers.


```python
'Monty Python and the Holy Grail' #single (or double) quotes indicate a string
```




    'Monty Python and the Holy Grail'




```python
"Monty Python and the Holy Grail"
```




    'Monty Python and the Holy Grail'




```python
sentence = "Monty Python \nand the Holy Grail" #\n is a special character denoting "new line"
sentence
```




    'Monty Python \nand the Holy Grail'




```python
print(sentence)
```

    Monty Python 
    and the Holy Grail



```python
2+2
```




    4




```python
'2'+'2'
```




    '22'




```python
'blah '*5
```




    'blah blah blah blah blah '




```python
ls st*
```

    string-slicing.png


# String slicing
<img src='string-slicing.png' width=600>


```python
name = 'Monty Python'
```


```python
name[0] #first character in the string
```




    'M'




```python
name[:5] #first 5 characters in the string
```




    'Monty'




```python
name[:-10] #up to the last 10 characters in the string (note \n counts as 1 character)
```




    'Mo'




```python
name[-6:] #The last 6 characters
```




    'Python'




```python
name[::-1] #Everything going backwards
```




    'nohtyP ytnoM'



Strings also have a number of built in methods including: 
* str.lower()
* str.upper()
* str.split()
* str.replace()
* str.strip()


```python
name.lower()
```




    'monty python'




```python
name.upper()
```




    'MONTY PYTHON'




```python
name.split() #This returns a list! We'll talk about that next. (By default splits on spaces)
```




    ['Monty', 'Python']




```python
name.split('y') #You can also split by other characters
```




    ['Mont', ' P', 'thon']




```python
name.replace('n', 'z')
```




    'Mozty Pythoz'




```python
name.strip() #Remove beginning/ ending whitespace
```




    'Monty Python'



# Lists
Python also has a number of compound data types such as lists. These are used to group items together.


```python
numbers = [1,2,3,4,5,6,7,8,9,10]
```


```python
numbers
```




    [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]




```python
type(numbers)
```




    list



Like strings, lists can be sliced by the index:


```python
numbers[0]
```




    1




```python
numbers[-1]
```




    10




```python
numbers[:5]
```




    [1, 2, 3, 4, 5]



# List methods
Lists also have many built in methods including:
* list.reverse()
    * Doesn't directly return anything but updates the list
* list.pop()
    * Remove the item at the given index (7) and return its value
* list.remove()
    * Find the given item and remove it. Doesn't return anything directly.
* list.append()
    * Append an item to the end of a list. No return value.
* list.insert()
    * Insert an item at a specific position.


```python
numbers = [1,2,3,4,5,6,7,8,9,10]
```


```python
numbers.sort()
numbers
```




    [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]




```python
numbers.reverse() #Doesn't directly return anything but updates the list
```


```python
numbers
```




    [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]




```python
numbers.pop(7) #Remove the item at the given index (7) and return its value
```




    3




```python
numbers
```




    [10, 9, 8, 7, 6, 5, 4, 2, 1]




```python
numbers.remove(7) #Find the given item and remove it. Doesn't return anything directly.
```


```python
numbers
```




    [10, 9, 8, 6, 5, 4, 2, 1]




```python
numbers.append(7)
```


```python
numbers
```




    [10, 9, 8, 6, 5, 4, 2, 1, 7]




```python
numbers.insert(-3, 3)
```


```python
numbers
```




    [10, 9, 8, 6, 5, 4, 3, 2, 1, 7]



# Loops and Iteration
Lists are a natural place to start looking at how we can iterate in python.


```python
for number in numbers:
    print(number)
```

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10



```python
for num in numbers:
    print(num+2)
```

    3
    4
    5
    6
    7
    8
    9
    10
    11
    12



```python
#Notice that we can use any alias as the variable name for our iterator:
for super_bad_variable_name in numbers:
    print(super_bad_variable_name)
```

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10


# Booleans and Conditionals
Another basic data type we have ignored up until now are booleans which are used in classical logic. Booleans are either True or False.


```python
type(True)
```




    bool




```python
type(False)
```




    bool



Booleans are very useful for conditional execution. For example:


```python
for i in [1,2,3,4,5]:
    if i < 3:
        print(i)
```

    1
    2


Through each iteration of the loop, python is evaluating the expression `i < 3` and resolving it to a boolean to determine whether or not to execute the following paragraph of code.


```python
1 < 3
```




    True




```python
2 < 3
```




    True




```python
3 < 3
```




    False




```python
4 < 3
```




    False




```python
5 < 3
```




    False


