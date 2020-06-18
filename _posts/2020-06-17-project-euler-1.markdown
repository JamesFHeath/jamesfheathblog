---
layout: post
title:  "Project Euler: Part 1"
categories: programming
tags: projecteuler math numbers
---

**Spoilers for [Project Euler](https://projecteuler.net/)**

### Problem 1

Project Euler [Problem 1](https://projecteuler.net/problem=1) is a simple place to start.
The problem is so sum all multiples of 3 and 5 under 1000.
For example, the sum of all multiples under 20 would be 3 + 5 + 6 + 9 + 10 + 12 + 15 + 18 = 78.

### Brute Force

The brute force approach is basically a recreation of [Fizz Buzz](https://en.wikipedia.org/wiki/Fizz_buzz). 
If you understand for loops and the modulo (%) operator, you are mostly set. 

{% highlight python %}
def solution(n):
    sum = 0
    for i in range(n):
        if i % 3 == 0 or i % 5 == 0:
            sum += i
    return sum

print(f'Sum of multiples of 3 and 5 below 1000: {solution(1000)}')
{% endhighlight %}
*Sum of multiples of 3 and 5 below 1000:* **233168**

### Finding a Formula
I remembered from CS Undergrad that [Gauss](https://en.wikipedia.org/wiki/Carl_Friedrich_Gauss) came up with a closed form solution for the numbers from 1 to n. 
Formula: <math>
    <mfrac>
        <mrow>
            <msup>
                <mi>n</mi>
                <mn>2</mn>
            </msup>
            <mo>+</mo><mi>n</mi>
        </mrow>
        <mrow><mn>2</mn></mrow>
    </mfrac></math>

#### Sidebar on the Formula
The insight here is that you can sum the numbers in pairs.
Let's try summing 1 to 10.
We can pair up 1 + 10, 2 + 9, 3 + 8... and they all add up to 11.
There will be 5 of these pairs, so the answer is 11 * 5 = 55.
To create the formula, we see that the pair sum will always be n + 1.
We need to add the pair 5 times, so it would be <math><mfrac>
    <mrow><mi>n</mi></mrow>
    <mrow><mn>2</mn></mrow>
</mfrac><mrow>
    <mo>(</mo>
    <mn>1</mn>
    <mo>+</mo>
    <mi>n</mi>
    <mo>)</mo>
</mrow></math>
or <math>
    <mfrac>
        <mrow>
            <msup>
                <mi>n</mi>
                <mn>2</mn>
            </msup>
            <mo>+</mo><mi>n</mi>
        </mrow>
        <mrow><mn>2</mn></mrow>
    </mfrac></math>.
If the number is odd, let's say 9, we pair up all the numbers except the middle.
1 + 9, 2 + 8, 3 + 7...we get a pair sum of 10 = 1 + n, and the leftover number is 5.
For odd numbers, we create n - 1 pairs. 
The formula is then the number of pairs times the value of the pairs divided by 2 plus the leftover 5.

1. <math>
    <mfrac>
        <mrow>
            <mi>n</mi>
            <mo>-</mo>
            <mn>1</mn>
        </mrow>
        <mrow><mn>2</mn></mrow>
    </mfrac>
    <mrow>
        <mo>(</mo>
        <mn>1</mn>
        <mo>+</mo>
        <mi>n</mi>
        <mo>)</mo>
    </mrow>
    <mo>+</mo>
    <mn>5</mn>
    </math>
2. <math>
    <mn>5</mn> 
    <mo>=</mo>
    <mfrac>
        <mrow>
            <mi>n</mi>
            <mo>+</mo>
            <mn>1</mn>
        </mrow>
        <mrow><mn>2</mn></mrow>
    </mfrac></math>

3. <math>
    <mfrac>
        <mrow>
            <mi>n</mi>
            <mo>-</mo>
            <mn>1</mn>
        </mrow>
        <mrow><mn>2</mn></mrow>
    </mfrac>
    <mrow>
        <mo>(</mo>
        <mn>1</mn>
        <mo>+</mo>
        <mi>n</mi>
        <mo>)</mo>
    </mrow>
    <mo>+</mo>
    <mfrac>
        <mrow>
            <mi>n</mi>
            <mo>+</mo>
            <mn>1</mn>
        </mrow>
        <mrow><mn>2</mn></mrow>
    </mfrac></math>
4. <math>
    <mfrac>
        <mrow>
            <msup>
                <mi>n</mi>
                <mn>2</mn>
            </msup>
            <mo>-</mo><mn>1</mn>
        </mrow>
        <mrow><mn>2</mn></mrow>
    </mfrac>
    <mo>+</mo> 
    <mfrac>
        <mrow>
            <mi>n</mi>
            <mo>+</mo>
            <mn>1</mn>
        </mrow>
        <mrow><mn>2</mn></mrow>
    </mfrac></math>
5. <math>
    <mfrac>
        <mrow>
            <msup>
                <mi>n</mi>
                <mn>2</mn>
            </msup>
            <mo>+</mo><mi>n</mi>
            <mo>+</mo><mn>1</mn>
            <mo>-</mo><mn>1</mn>
        </mrow>
        <mrow><mn>2</mn></mrow>
    </mfrac></math>
6. <math>
    <mfrac>
        <mrow>
            <msup>
                <mi>n</mi>
                <mn>2</mn>
            </msup>
            <mo>+</mo><mi>n</mi>
        </mrow>
        <mrow><mn>2</mn></mrow>
    </mfrac></math>

#### Back to Finding a Formula
I attempted to tweak this equation in order to get a result to only sum multiples of 3.
Then I could add that to the sum of all multiples of 5, and then subtract the sum of all multiples of 15.
A promising step was <math>
    <mfrac>
        <mrow>
            <msup>
                <mi>n</mi>
                <mn>2</mn>
            </msup>
            <mo>+</mo><mi>n</mi>
        </mrow>
        <mrow>
            <mn>2</mn>
            <mo>*</mo>
            <mn>3</mn>
        </mrow>
    </mfrac></math>, where the 3 could be replaced with 5 and 15 to get the sum.
This gave a very close answer, but not an exact answer. 
The lighbulb moment came when I made a list of the numbers 1 to 10 to try and see if the 3s could be paired up in a similar way to all the integers. 
I finally realized that if I knew the count of the 3s under a certain number, I could then perform the <math>
    <mfrac>
        <mrow>
            <msup>
                <mi>n</mi>
                <mn>2</mn>
            </msup>
            <mo>+</mo><mi>n</mi>
        </mrow>
        <mrow><mn>2</mn></mrow>
    </mfrac></math> equation on them, then multiply the answer by 3.
1, 2, **3**, 4, 5, **6**, 7, 8, **9**, 10 reduces to (1 + 2 + 3)(3) = 3 + 6 + 9.
I just needed to divide n by 3, cut out the remainder, apply the Gauss formula, and multiply the result by 3.
I could do the same for 5 and 15, then combined the answers. 

### Python Closed Form Solution

{% highlight python %}
def sum(n, m):
     return (((n // m)**2 + (n // m)) / 2) * m

print(sum(999, 3) + sum(999, 5) - sum(999, 15))
{% endhighlight %}
**233168.0**