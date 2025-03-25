# Challange

Suppose there are n people standing in a circle and they are numbered 1 through n in order.

Person 1 starts off with a sword and kills person 2. He then passes the sword to the next person still standing, in this case person 3. Person 3 then uses the sword to kill person 4, and passes it to person 5. This pattern continues around and around the circle until just one person remains.

What is the number of this person?
Example:

For n = 5, the result should be 3.

1 kills 2, passes to 3.
3 kills 4, passes to 5.
5 kills 1, passes to 3.
3 kills 5 and wins.

Input/Output

    [input] integer n

The number of people. 1 through n standing in a circle.

1 <= n <= 1e9

    [output] an integer

The index of the last person standing.

# Solution

```python
import array

def circle_slash(n):
    #Creating array of int from 1 to n
    if n == 1:
        return 1

    # Josephus problem for k = 2 https://en.wikipedia.org/wiki/Josephus_problem
    # f(n) = 2l+1,  n = 2^m + l, 0<=l<2^m
    m = 0
    while True:
        print(f'm:{m},n:{n}')
        if 2**m > n:
            m -= 1
            break
        else:
            m += 1

    l = (n - (2**m))
    print(f'm:{m},n:{n},l:{l}')
    result = 2*l+1
    return (result)

```
