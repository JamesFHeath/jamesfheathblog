---
layout: post
title:  "Project Euler: Part 9"
categories: programming
tags: projecteuler math numbers
---

**Spoilers for [Project Euler](https://projecteuler.net/)**

### Problem 9

Project Euler [Problem 9](https://projecteuler.net/problem=9) is a problem about Pythagorean Triples. 
A Pythagorean Triple is a set of 3 integers that satisfy the equation <math><msup><mi>a</mi><mn>2</mn></msup><mo>+</mo><msup><mi>b</mi><mn>2</mn></msup><mo>=</mo><msup><mi>c</mi><mn>2</mn></msup></math> where <math><mi>a</mi><mo><</mo><mi>b</mi><mo><</mo><mi>c</mi></math>.
The goal is to find the product <math><mi>a</mi><mi>b</mi><mi>c</mi></math> of the only Pythagorean Triplet that satisfies <math><mi>a</mi><mo>+</mo><mi>b</mi><mo>+</mo>c<mo>=</mo><mn>1000</mn></math>.

### Finding an Equation
The problem gives us two equations and three variables, so we're not going to be able to solve it with just algebraic manipulation.
My approach was to try to find the value of c that would match a pair of values for a, b.
The first equation becomes <math><mi>c</mi><mo>=</mo><mn>1000</mn><mo>-</mo><mi>a</mi><mo>-</mo><mi>b</mi></math>.
Once we have some values for c, we can plug it into the Pythagorean formula to see if we get appropriate values. 

### Python Code

This approach just goes through a pair of for loops.
We don't need to go through every possible number 1 to 1000 because we know the max value for a is 332 and b is a 499.
{% highlight python %}
for a in range(333):
    for b in range(500):
        ans_1 = equation_1(a, b)
        ans_2 = equation_2(a, b)
        if ans_1 ** 2 == ans_2:
            print(a)
            print(b)
            print(ans_1)

def equation_1(a, b):
    return 1000 - a - b

def equation_2(a, b):
    return a**2 + b**2
{% endhighlight %}
**200**<br>
**375**<br>
**425**<br>
**31875000**<br>