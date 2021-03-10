# Lecture 2  Idiomatic Python

* By Code Creators

---

## Welcome Back

* mentoring session
* the exercise
* slides
* feedback form

Note: Other stuff, Links are in the discord

---

## Previously

* installed python

* installed *<A TEXT EDITOR*

* installed git

* cloned a repo

* (optionally) fixed some terrible code

* (even more optionally) found some palindromes

---

## This Week

* Naming things

* writing pythonically

* using modules and pip

---


## "My code is absolutely fine! it works and I understand it just fine"

* sound familiar ?

* writing better code takes time but is worth it 

* better code takes care

* how do we do this ? 

Note:
---


## How can we write better python ?

* *zen*
* name things better 
* format your code 
* simplify your code
* write comments
* use idioms

>>>

## Zen

```python
import this

"""
Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
"""

```

---

## Naming Things 

* naming things is hard 
* doing it right is worth it

Note:
hilarious joke: 2 difficult things
cache invalidation
naming things and off by one errors

go vertically after this

>>>

## Naming Things - Follow PEP8
* functions should be `lowercase_with_underscores`
* Classes should be `CapitalisedLikeThis`
* Constants should be `ALL_CAPS`

>>>

## Naming Things - Pronouncable

this 

`data_rcrd_106 = ...`

could be 

`customer_data = ...`

>>>


## Naming Things - Clear and Decriptive with Intent

```python
d = 5
w_left = 6
for nme in names:
    ...
```
could instead be:

```python

days_remaining = 5
weeks_remaining = 6

for name in people:
    ...
```
Note: also add  Meaningful distinctions

>>>

## Naming Things - Searchable

```python
for j in range(34):
    s += (t[j]*4)/5;

```
to
```python
real_days_per_ideal_day = 4;
WORK_DAYS_PER_WEEK = 5;
sum_of_total_weeks = 0;

for estimate in task_estimations
    real_task_days = estimate * real_days_per_ideal_day;
    real_task_weeks = real_task_days / WORK_DAYS_PER_WEEK;
    sum_of_real_weeks_spent += real_task_weeks;
```

>>>

## Naming Things - Consistent

* avoid 
```python
def find_name(person):
    ...

def retrive_employee(employee):
    ...

```

* instead 
```python
def get_name(id):
    ...

def get_employee(employee_id):
    ...

```
Note: be consistent, use one word per concept

## Naming Things - Avoid Mental Mapping

```python
# change this
for x in names:
    ...

# into this 
for person in employees:
    ...

```

Note: reduce the information you have to hold in your head while coding 
>>>


## Naming Things - Don't Lie

from this

```python
account_list_group = {"id": 5, ... }


```
to this

```python
accounts = {"id": 5, ...}
```

---


## 

* writing things "the python way" 

* makes code consistent between people

* less you have to keep track of

>>>

## if, else

* Don't 

```python 
if len(records) == 0:
    ... 

if is_complete == True:
    ... 

if name == "Jack" or name == "Nam" or name == "Sam":
    print("this is a Programme Developer")

```

* Do

```python 
if not records:
    ...

if is_complete:
    ...

if name in ("Jack", "Nam", "Sam"):
    print("this is a Programme Developer")
```

>>>

## for loops

* Don't

```python

# iterate over ranges of lists
while i < len(books):
    print(books[i])
    i += 1

# use and update separate index variable
index = 0
for i in "a really long word":
   print("letter number", index, "is", i) 
   index += 1

```

* Do

```python

# use in to iterate over an iterable
for book in library:
    print(book)

# use enumerate to get an index variable more easily
for i, letter in enumerate( word ):
    message = "letter number {index}, is {letter}".format(index=i, letter=letter) 
    print(message)

```

>>>

## Comprehensions


* Don't

```python

names_of_employees = []

for person in employees:
    names_of_employees.append(person.name)

user_email = {}
for user in users_list:
    if user.email:
        user_email[user.name] = user.email
 
```

* Do

```python

names_of_employees = [person.name for person in employees]

user_email = {user.name: user.email for user in user_list if user.email}
```

>>>

## Dividing up Lists

* Don't

```python

some_list = ['a', 'b', 'c', 'd', 'e']
(first, second, rest) = some_list[0], some_list[1], some_list[2:]
print(rest)
(first, middle, last) = some_list[0], some_list[1:-1], some_list[-1]
print(middle)
(head, penultimate, last) = some_list[:-2], some_list[-2], some_list[-1]

```


* Do

```python

some_list = ['a', 'b', 'c', 'd', 'e']

(first, second, *rest) = some_list
print(rest)
(first, *middle, last) = some_list
print(middle)
(*head, penultimate, last) = some_list

```

---

## make good use of libraries

* python has amazing libraries
* `pip install numpy` if you want to install numpy





