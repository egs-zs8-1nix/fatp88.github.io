---
layout: single
title: NumPy is absolute magic
excerpt: "NumPy is a python library uncommonly used for data analysis since other libraries built on top of it, like Pandas, are more useful, however their speed are thanks to NumPy inner looping optimization. This is achieved by Vectorization and Broadcasting. However, why does it really works in a computer?"
date: 2022-07-06
classes: wide
header:
  teaser: /assets/images/htb-writeup-ready/ready_logo.png
  teaser_home_page: true
  icon: /assets/images/hackthebox.webp
categories:
  - NumPy
  - Data Analysis
tags:
  - python
  - libraries
  - tools
  - numpy
  - vectorization
  - looping
---

![](/assets/images/htb-writeup-ready/ready_logo.png)

## NumPy is absolute magic.

For my first blog entry, I'd like to talk about NumPy, a python library used for mathematical operations.

Personally, all this sounds like alien stuff to me, so I wanted to know more about the "*python is slow, numpy makes it faster*" thing I've heard a lot while starting my data analysis studies.

This is what I found after some research.

The way a program operates stuff with data, specially data arrays, is having loops for calculations. *Making it easier, making it *faster is what designers try to achieve.
NumPy works with 2 concepts: **Vectorization** and **Broadcasting**.
The loops are inevitable, but they can be improved for faster calculations and, better mathematical visualization of a code.

Thats good, it makes sense, but doesn't tell me how exactly this is achieved.

If I have a loop, and make it better, it will show the same problems a loop has. Why is necessary to change it?

Like an oasis in the middle of the desert, ***Beautiful Code***, written by Andy Oram and Greg Wilson, in its chapter 14 gives an explanation.

NumPy works with the idea of arrays, and the code execution is optimized on the loop over a single dimension where simple striding can be assumed.
In simpler words, Numpy makes two things, return a modified iterator and remove dimensions from an iteration.
By doing so, the outer loop iterations will be reduced and inner loop iterations will be faster.

However, the bottleneck here is the time needed to input or output data from memory for all purpose processors. And here comes the magic: NumPy makes sure the inner loop proceeds with data as close as possible. This makes the inner loop optimized for speed. As how does it work in a computer, you can say it works with a form of parallelism, either SIMD or BLAS, auto Vectorization, etc. So it doesn't thread but loop. And those loops are incredibly fast.


Now tell me, how is this anything but magic?


This is not in the scope of Data Analysis, but admittedly, now I know that NumPy is a lot more than a "fast thing" I'll use from now on. I got into themes like parallelism, SIMD and api programming just by looking this up. 


### References:
 - Beautiful Code by Andy Oram, Greg Wilson. Chapter 19: "Multidimensional Iterators in Numpy".  O'Reilly Media Inc. 2007. ISBN: 978-0-5965-1005-6

 - Python Data Analytics by Fabio Nell. Chapter 3:"The Numpy library". Apress Media 2015. ISBN-13 (pbk): 978-1-4842-0959-2 ISBN-13 (electronic): 978-1-4842-0958-5

 - https://numpy.org/doc/stable/reference/arrays.ndarray.html

 - https://numpy.org/doc/stable/numpy-user.pdf

 - https://morioh.com/p/70493e6bfaed

 - https://en.wikipedia.org/wiki/Single_instruction,_multiple_data

 - https://en.wikipedia.org/wiki/Vector_processor

 - https://stackoverflow.com/questions/14259737/what-is-the-relationship-between-vectorization-and-embarrasingly-parallel

 - https://insidebigdata.com/2017/09/20/importance-vectorization-resurfaces/

 - https://www.quantifisolutions.com/vectorization-part-2-why-and-what/

 - https://www.upgrad.com/blog/vectorization-and-broadcasting-in-python/#:~:text=Vectorization%20and%20Broadcasting%20are%20ways,don't%20face%20any%20bottlenecks.


