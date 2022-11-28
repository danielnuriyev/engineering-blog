# Difference between a computer scientist and an engineer

## Difference 1

A computer scientist is a mathematician who designs solutions in mathematically most efficient way 
given constraints such time, tools, people, budget.

A software engineer is a handyman who learns and uses tools to achieve goals given the same contraints.

Of course, a computer scientist is usually an engineer and an engineer is not necessarily just a handyman but here I will juxtapose these terms. 

The difference is in the way of thinking. Given the same task, both will produce results that looks the same on the outside but are fundamentally different in how it works.

Example: write a function that finds the greatest even number in an array.

Engineer:

```python

def find_max_even(numbers):

  # For the purpose of the example, let's assume that numbers is iterable and consists of numbers
  
  numbers.sort()
  for n in reversed(numbers):
    if n != 0 and n % 2 == 0:
      return n
  return None

```

This ^ is based on tens of real life examples of software engineering interviewees. I have seen worse, BTW.

A person who thinks as a computer scientist will write:

```python

def find_max_even(numbers):

  mx = None
  for n in numbers:
    if n != 0 and n % 2 == 0:
      if mx is not None and n > mx:
        mx = n
      elif mx is None:
        mx = n
     
  return mx

```

The difference is that the latter example loops over the array maximum 1 time having the worst time of O(n), 
whereas a best sorting algorithm runs for O(n log n) and then the code may do another loop if there are no even numbers.

These examples also demonstrate that thinking as a computer scientist is not necessarily more time consuming.

## Difference 2

An engineer asks "what it does". A computer scientist asks "how it works".

When a piece of hardware or software can do something, it does not mean that you should use it because of how it works inside 
because it may affect the performance, budget, scaleability of your final output.

Example: you need to write a REST API that stores and retrieves data. The API must be fast, highly concurrent, scaleable, cheap.
What questions will you ask yourself? What language will you pick and why? What cloud provider (AWS, GCP, Azure, Oracle etc.) 
and what technology (lambda, ec2 etc.) will you pick and why?

A common choice of an engineer is AWS + lambda + nodejs.
Choosing a common and simple solution has its benefits.
But it is quite possible that a REST API in Go on an EC2 can handle way higher concurrency and spikes simply because of how concurrency is implemented in Go.
(Other aspects must be taken into account, of course).
How concurrency is implemented inside a language is not something that a handyman thinks about.

## Is it necessary

If you do not train yourself to think as a computer scientist starting with your first job:
- other engineers may notice that
- you will not be able to design efficient, scaleable and complex stuff if you rely on cloud, library and language designers

It will become a bottleneck in your career even if you take a management track.

The bottleneck is not the lack of knowledge because no one knows everything. 

**The bottleneck is the way of looking at things and ways of thinking about them.**
