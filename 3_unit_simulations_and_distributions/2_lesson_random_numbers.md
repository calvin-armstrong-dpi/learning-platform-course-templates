Python provides the ability to create randomness by generating random numbers or picking randomly from a list. To
utilize random numbers in Python, we must `import` a new library:
```py
    # Import the random library, allowing the use of functions that generate random numbers
    import random
```

Generating Random Numbers Using `random.randint`
------------------------------------------------

One of the primary ways we generate random numbers in Python is to generate a random integer (whole number) within a
specified range. For example, if I want to generate a number to simulate the roll of a six-sided die, I need to generate
a number in the range 1-6 (including the endpoints 1 and 6). With the `random` library, this is possible:
```py
    # Randomly generates a number in the range 1-6, including the end points:
    random.randint(1, 6)
```

A **new random number** will be generated **every time this code runs**. This means that you might get `2` and then
another `2` (just like it's possible to roll `2` twice in a row), but it's more likely that the second number you get
will not be a `2`.

The `random.randint` function will always **generate numbers with equal probability** for each number within the range.
This means that the probability of getting any specific number when running `random.randint(1, 10)` is only 10% -- since
each of the numbers 1-10 are each 10% likely to show up.
```py
    # Randomly generates a number in the range 1-10, including the end points:
    random.randint(1, 10)
```
When you generate a generate many random numbers, you'll expect to see a random distribution of numbers and some areas
where the same number appears many times in a row. Here's the output of running `random.randint(1, 6)` to generate a
number in the range 1-6 a total of 100 times:
```py
    import random
    random.randint(1, 6)
    # ...and running the code 100 times:


    1  # Our very first roll was a 1!
    4
    3
    6
    6  # This is the first time with two numbers in a row...
    3
    3
    3  # ...followed by three 3s in a row!
    5
    3
    5
    4
    6
    2  # It took 14 rolls before our first 2 was rolled.
    4
    3
    2
    5  # We rolled a 5 here on the 18th roll...
    4
    1
    6
    3
    4
    1
    3
    2
    4
    1
    6
    6
    3
    6
    2
    4
    2
    3
    3
    1
    3
    1
    3
    3
    5  #...and then we don't roll another 5 for 25 rolls!
    2
    4
    2
    3
    5 
    5 # This is the longest sequence in the whole set (four 5s).
    5 # ...for any set of 100 dice rolls, we expect a run of four  
    5 # to happen about once. (We can simulate this later!)  
    2
    4
    1 # However, it is not as rare to have runs of exactly three.
    1 # (A run of exactly three occurred twice this set of 100 numbers:
    1 # 3s on rolls {7,8,9} and then these 1s on rolls {54, 55, 56}.)
    2
    6
    6
    1
    6
    3
    5
    4
    1
    2
    5
    1
    4
    1
    5
    5
    3
    3
    2
    4
    4
    5
    2
    5
    2
    6
    3
    6
    5
    2
    5
    2
    5
    1  # The last roll of a 1 -- there is 14 rolls of a 1.
    6  # The last roll of a 6 -- there is only 13 rolls of a 6.
    5
    3
    3  # The last roll of a 3, the most popular number -- rolled 21 times!
    2
    5
    5  # The last roll of a 5 -- there is 20 rolls of a 5.
    4  # The last roll of a 4 -- there is 14 rolls of a 4.
    2
    2  # The last roll of a 2 -- there is 18 rolls of a 2.
```

One hundred randomly generated numbers using `random.radint(1, 6)`, with comments added.

Generating Random Numbers Using `random.choice`
-----------------------------------------------

When we need more control over the random number generation, `random.choice` requires a list to be specified and Python
will **randomly choose one value from the list**. For example, we can still simulate rolling a six sided die:
```py
    # Randomly generates a number in the range 1-6, including the end points:
    random.choice( [1, 2, 3, 4, 5, 6] )
```

However, suppose we want to **cheat**! What if we designed a dice what is **twice as likely to land on a six than normal
**. To account for this, we can add a second six to `random.choice`:
```py
    # An unfair die, twice as likely to roll a 6 than any other value:
    random.choice( [1, 2, 3, 4, 5, 6, 6] )
    #                                ^^- An extra 6 was added!
```

### Generating Random Strings Using `random.choice`

Python will pull any element from the list when using `random.choice`, so it does not always have to be a number! For
example, if we want Python to flip a coin that has a `"heads"` and `"tails"` side, we can still use `random.choice`:
```py
    random.choice( ["heads", "tails"] )
```

Remember that Python is equally likely to pull any element form the list -- so this would be a fair coin, as there will
be a 50% chance for "heads" and 50% for "tails".

* * *

Example Walk-Throughs with Worksheets
=====================================

### Video 1: Random Numbers in Python

Follow along with the worksheet to work through the problem:

* [Download Blank Worksheet (PDF)](/static/worksheets/m3/m3-02a_Examples Using Random Numbers in Python.pdf)

* * *