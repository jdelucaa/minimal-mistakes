---
title: "Post: Standard"
excerpt_separator: "<!--more-->"
categories:
  - Post Formats
tags:
  - Post Formats
  - readability
  - standard
---

During a technical interview or even while playing with code, you may (have to) come up with different solutions to the same problem. You may change your solution to make it easier to code or just to make it look better. However, there is another way of comparing all these different solutions or algorithms that is much more concrete, that's *Runtime Complexity*.

#### But what the heck is Runtime Complexity?

In many different interviews, many times, you're going to be asked what the runtime complexity of a give solution is. Runtime Complexity describes the performance of an algorithm. You can start to compare the performance of an algorithm by asking yourself: "How much more processing power/time is required to run my algorithm if I double the inputs?".

So, let's look at some examples and try to answer this question.

### String Reverse (iterative solution):

```yaml
function reverse(str) {
  let reversed = '';

  for (let char of str) {
    reversed = char + reversed;
  }

  return reversed;
}
```
Here, we iterate through each character of the string exactly one time. Each additional character is equal to 1 step through 1 loop. This would be 'N', or 'linear' runtime because it's exactly one to one (add 1 to the input and have 1 additional step of work).

### Steps Algorithm:

```yaml
function steps(s) {
  for (let row = 0; row < s; row++) {
    let stair = '';

    for (let col = 0; col < s; col++) {
      if (col <= row) {
        stair += '#';
      } else {
        stair += ' ';
      }
    }
    console.log(stair);
  }
}
```
This algorithm builds a string that looks like a stair, for example:

```yaml
'#   '
'##  '
'### '
'####'
```

To build a stair like the example above, our input 's' has to be 4 and as we can see in the output stair, we have 16 characters counting all the '#' and the ' '. That basically means that this would be n^2, or quadratic runtime. As 's' increases by 1, we have to do way more stuff, or 's * s' things total.

There are other runtime that exist:

![](/assets/images/alg-tab.jpg)

### Constant time (1):
No matter what input we give, it's always going to take the same amount of time to execute the algorithm.

### Logarithmic time (log(n)):
Doubling the number of elements we are iterating over doesn't double the amount of work. Alwas assume that searching operations are log(n) (searching through a sorted array, for example).

### Linear time (n):
Linear time is one of the most common run times. Iterates through all elements in a collection of data. If you see a loop from 0 to array.length, you probably have 'n', or linear runtime. Like the string reverse example above, it's a one to one time to complete the algorithm.

### Quasilinear time (n * log(n)):
Doubling the number of elements we are iterating over doesn't double the amount of work. If we start to increase our input set by 1, increase the amount of time it took to execute the algorithm by one plus a little bit. Many types of sorting algorithms are usually going to be working with n * log(n).

### Quadratic time (n^2):
Like the steps example above, every element in a collection has to be compared to every other element. 'The handshake problem', an easy way to picture this: Imagine a group of people standing in a room. If you send an additional person into that room and you introduce that new person to everyone else and you have them shake hands, that would be quadratic complexity.

### Exponential time (2^n):
If you add a single element to a collection, the processing power required doubles. This is the worst case, this is what we would want to avoid. I will probably going to post some examples in my next posts about runtime complexity.

------------------
------------------

This was just a quick introduction, just a quick review of the very common runtime we see in action. I will continue on this subject in my next post, where I am going to show other more complicated algorithms to start to get into this world of runtime complexity.