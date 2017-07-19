---
layout: post
title:  "Hitchhiker's Guide to Competitive Programming"
date:   2017-07-06
categories: competitive-programming
author: udit
---

# Introduction

Competitive programming is the quintessential Computer Science sport. It is the geek version of your favorite sport, be it Cricket or Football or whatever. The level of competition is fierce and the passion among the participants is awesome. Also, it is a really fun way to meet and socialize with some really cool people. NITH has regular programming meetups where anyone interested can come and solve really hard problems in really short amounts of time with kindred spirits. CP is also a really good method of adding some challenges into the generally laid-back life of a CS student at NITH.

Besides, if one wants to look at actual material advantages of competitive programming, look no further than interviews at top CS companies. To a person who has been taking part in programming contests for her entire college career, the questions asked in these interviews will generally seem to be easy mode (ok, maybe not, but the problems won't seem impossibly hard, at least).


The very first thing one should note is that this guide is only meant to help you get started with competitive programming and not meant to explain concepts in detail. Anyone interested in further reading can refer to the resources provided at the very end of this guide.

---

# Prerequisite

The only prerequisite to getting started with CP is basic knowledge of a programming language. Generally, C, C++, JAVA and PYTHON are used for CP. We'll use C++. The reason behind using C++ and not C is that C++ contains templates of certain frequently used Algorithms and Data Structures, commonly known as STL. Using them makes the code smaller and easier to debug. Also, PYTHON is helpful in problems with big integers.

##  Some Language tutorials:

+   **PYTHON :** [HackerEarth](https://www.hackerearth.com/practice/python/), [Python Documentation](https://docs.python.org/3/tutorial/index.html)

+	**C++ :** [LearnCpp](http://www.learncpp.com/)

+   **STL :** [HackerEarth](https://www.hackerearth.com/practice/notes/standard-template-library/)

+   **C Video Lectures :** [CS50](https://www.youtube.com/watch?v=o4SGkB_8fFs&list=PLhQjrBD2T382VRUw5ZpSxQSFrxMOdFObl) (Also gets you familiar with other fundamentals of Comp. Science).

---

# Online Platforms

## Practice:

+   **[SPOJ](https://www.spoj.com) :** 

    +   Contains a lot of programming problems of varied difficulty.

    +   Start with problems having maximum submissions and move on to ones with lesser submissions once you build some confidence.  

    +   Start participating in Codechef and Codeforces contests once you have solved at least **30-40** problems.

+   **[CodeMonk](https://www.hackerearth.com/practice/codemonk/) :**

    +   Contains both tutorials and problems of basic Algorithms and Data Structures.

    +   Tutorials are easy to understand and covers most of the topic.

    +   Can be easily completed within a month or two.

    +   A **'must do'** for beginners.

+   **[A2OJ](https://www.a2oj.com) :**

    +   We are often unable to find good problems of a particular topic, that's where a2oj comes to rescue.

    +   Problems are from online judges like SPOJ, UVa, Codeforces and are classified according to topic and difficulty.

## Contests:

+   **[Codechef](https://www.codechef.com) :**

    +   Organizes 3 rated contests every month, namely, Long Challenge(10 days), LunchTime(3 hrs) and Cook-Off(2.5 hrs).

    +   Long Challenge is best for learning new concepts and improving known ones. Do participate in Long Challenge every month and do read editorials of problems not solved during contest and try to solve them.

    +   Short contests are best for improving speed and accuracy.

+   **[Codeforces](http://codeforces.com/) :**

    +   4-5 Shorts contests(2 hrs) every month.

    +   Very effective in improving speed and accuracy.

    +   Less time, more problems and more participants makes it tougher and more interesting than Codechef.

+	**[Heuristics](https://www.hackerearth.com/challenge/college/csec-heuristics-0/) :**

    +   Monthly contest organized by CSEC on HackerEarth.

    +   2-3 hrs long and consists of 4-6 problems of varied difficulty.

    +   Editorials are also posted with source on either CSEC blog or on HackerEarth.
    
---

# Getting Started

In order to solve a problem, you first read the problem, code the solution and submit the solution online. A verdict is shown from which you can see how your code performed against the test cases ran by the online judge.

## Problem Statement:

Statement starts with few paragraphs explaining the problem. Read it thoroughly until you understand what is to be solved.

After that, there's *Input and output* format explaining how input and output is formatted. NEVER output anything else than what is asked. For example, do not print stuff like "Enter a number: ".

Then, *Constraints* are given which will give you the idea of how big the input is and whether your approach will work or not. 
Constraints include --
+   **Time limit :** Given in *seconds*. Time less than which your code should calculate and print the output.

+   **Memory limit :** Given in *MB*. Maximum amount of memory your code should use.

+   **Input Size :** Maximum possible input size, ie, input bigger than this won't be there in test cases.

Then, there will be *Sample Input* and *Sample Output* to give you an idea of I/O formats and to give you a better understanding of the problem.

Lastly, there will be *Explanation*(might be absent) which explains how sample output is calculated.

## Solving the problem:

After reading and understanding the problem, a solution is to be coded for it. A given problem can have many possible solutions but you have to find that solution which comes under the constraints. In order to see if your code fulfills the time and memory limits, you need to do a *Complexity Analysis* of your solution.

**Runtime Complexity Analysis :** 
Complexity of a solution is a measure of it's runtime or number of operations as a function of input size. Let's take an example, Suppose we have to find the maximum among $$N$$ positive numbers.

```
int ans = -1,x;
for(int i=0;i<N;i++) {
    scanf(“%d”,&x);
    ans = max(ans, x);
}
```

$$N$$ times checking $$i < N$$.

$$N$$ times checking max of ans and x.

$$N$$ times i++.

$$N$$ times scanf.

Hence, total number of operations is $$4 * N$$. We only care about dependency on $$N$$. Therefore, order is $$O(N)$$.

[CLRS](https://en.wikipedia.org/wiki/Introduction_to_Algorithms) is having detailed theoretical explanation on Complexity Analysis.
Also, for most of the online judges(SPOJ, Codechef etc), number of operations in 1 sec is approximately $$10^8$$.
In some problems, there are T test cases in one input file. If a solution is having order of $$O(N^3)$$, then total order of the whole input will be $$O(T * N^3)$$.

For Example, if T < 100 and N < $$10^5$$, and order per test case is $$O(N)$$, then number of operations will be at max $$10^5$$ per test case and $$10^7$$ per input file.

## Verdict:

Once you submit your solution, the judge will run a few test cases on your solution and will give you a verdict based on the output of your solution.

**There will be one of following verdicts :**
+   **AC**(Also shown by a green tick): Your solution is accepted.

+   **WA**(Also shown by a red cross): Your code gives wrong output. Check for correctness of your approach.

+   **TLE**(Also shown by a clock): Your code is taking more time than the given limit. You need to code a faster solution.

+   **Run time error**: This could occur due to-

    +   Segmentation fault which could be due to declaring array of size smaller than required or accessing negative indices.

    +   Dividing by zero.

    +   Declaring arrays of size more than $$10^8$$.

+   **Compilation Error**: Could be due to wrong language selection or some syntax error. Check the language selected and run it on your PC first and fix syntax errors.

Now, for a warm up, try this problem - [TEST](https://www.codechef.com/problems/TEST).

Few more problems to get you familiar with problem solving--

+	[https://www.codechef.com/problems/HS08TEST](https://www.codechef.com/problems/HS08TEST)

+	[https://www.codechef.com/problems/FLOW001](https://www.codechef.com/problems/FLOW001)

+	[https://www.codechef.com/problems/INTEST](https://www.codechef.com/problems/INTEST)

+	[https://www.codechef.com/problems/FLOW017](https://www.codechef.com/problems/FLOW017)

---

# Using STL(Standard Template Library)

Certain Data Structures and functions are frequently used while coding solutions. Standard Template Library, commonly known as STL, is basically a collection of few frequently used functions and data structures that can be used directly. This reduces the effort significantly. Also, they are very easy to use and makes the code compact and clean which can be easily debugged.

**Data Structures:**

+   **Vector :** [GeeksForGeeks](http://www.geeksforgeeks.org/vector-in-cpp-stl/), [CppReference](http://en.cppreference.com/w/cpp/container/vector)

+   **Pair :** [GeeksForGeeks](http://www.geeksforgeeks.org/pair-in-cpp-stl/), [CppReference](http://en.cppreference.com/w/cpp/utility/pair)

+   **Stack :** [GeeksForGeeks](http://www.geeksforgeeks.org/stack-in-cpp-stl/), [CppReference](http://en.cppreference.com/w/cpp/container/stack)

+   **Queue :** [GeeksForGeeks](http://www.geeksforgeeks.org/queue-cpp-stl/), [CppReference](http://en.cppreference.com/w/cpp/container/queue)

+   **Priority Queue :** [GeeksForGeeks](http://www.geeksforgeeks.org/priority-queue-in-cpp-stl/), [CppReference](http://en.cppreference.com/w/cpp/container/priority_queue)

+   **Set :** [GeeksForGeeks](http://www.geeksforgeeks.org/set-associative-containers-the-c-standard-template-library-stl/), [CppReference](http://en.cppreference.com/w/cpp/container/set)

+   **Map :** [GeeksForGeeks](http://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/), [CppReference](http://en.cppreference.com/w/cpp/container/map)

**Functions:**

+   **sort :** [GeeksForGeeks](http://www.geeksforgeeks.org/sort-c-stl/), [CppReference](http://en.cppreference.com/w/cpp/algorithm/sort)

+   **memset :** [GeeksForGeeks](http://www.geeksforgeeks.org/memset-c-example/), [CppReference](http://en.cppreference.com/w/cpp/string/byte/memset)

+   **binary_search :** [GeeksForGeeks](http://www.geeksforgeeks.org/binary-search-algorithms-the-c-standard-template-library-stl/), [CppReference](http://en.cppreference.com/w/cpp/algorithm/binary_search)

+   **lower_bound, upper_bound :** [GeeksForGeeks](http://www.geeksforgeeks.org/binary-search-functions-in-c-stl-binary_search-lower_bound-and-upper_bound/), [CppReference](http://en.cppreference.com/w/cpp/algorithm/upper_bound)

Also, you might be wondering that which header files are these data structures and functions part of. Each of the above mentioned data structure and function is having it's own header file. But, instead of adding header file for each of them, one can just add a single header file.

```
#include <bits/stdc++.h>
```

Few problems that can be solved easily using STL--

+   **Vector:**

	[The Monk and Class Marks - HackerEarth](https://www.hackerearth.com/problem/algorithm/the-monk-and-class-marks/)

+   **Set:**

	[Monk's Birthday Party - HackerEarth](https://www.hackerearth.com/problem/algorithm/monks-birthday-party/)

+   **Map:**

	[Tourist Translations - Codechef](https://www.codechef.com/MARCH13/problems/TOTR/)

+   **Stack:**

	[Compilers and parsers - Codechef](https://www.codechef.com/MAY14/problems/COMPILER)

+   **Queue:**

	[Monk and Power of Time - Hackerearth](https://www.hackerearth.com/practice/data-structures/arrays/1-d/practice-problems/algorithm/monk-and-power-of-time/)

+   **Priority Queue:**

	[Monk and the Magical Candy Bags - HackerEarth](https://www.hackerearth.com/practice/data-structures/trees/heapspriority-queues/practice-problems/algorithm/monk-and-the-magical-candy-bags/)

---

# Common Mistakes and Errors

"Anyone who has never made a mistake has never tried anything new."      

-- Albert Einstein

Following are few frequently encountered mistakes and errors while writing codes--

+   **Not including header file for a function or data structure.** Results in compilation error.

+   **Not initializing variables.** While calculating values like sum or factorial, using uninitialized variables can result in wrong answer.

+   **Declaring arrays of size smaller than required.** This results in Runtime Error. Check if array size is enough for all possible test cases and increase it, if required.

+   **Declaring arrays of large fix sizes ($$~ 10^4$$ to $$10^7$$) inside main.** This causes segmentation fault and can be fixed by declaring array outside of main. The reason being that variables declared inside main goes into stack and outside goes into heap inside the memory. Stack is smaller in size as compared to heap and stack overflow occurs when array of large size is declared inside of main. 

+   **Using int in place of long long and float in place of double.** Using int when an integer having value greater than $$2 * 10^9$$ is to be stored will cause an integer overflow and program will give Wrong answer. Use long long when integer is upto $$10^{18}$$. Double is having more precision as compared to float and hence, must be preferred over float.

+   **Comparing floats or doubles.** Float and double do not have infinite precision. One can't just directly check for two floating point values for equality.

Instead of
```
double a, b;
scanf("%lf%lf", &a, &b);
if(a == b) {
    //statements
}
```

Use
```
double a, b;
scanf("%lf%lf", &a, &b);
if(fabs(a - b) < 0.000001) {
    //statements
}
```

**fabs()** calculates the absolute diff in a and b. If values are equal, diff will be negligible and above condition will be true. For a more accurate result, one can use [Epsilon](http://en.cppreference.com/w/cpp/types/numeric_limits/epsilon), but in most cases, above method will do.

---

# Important Algorithms and Data Structures

Following are a few links to introductory part of most common topics in algorithms and data structures --

+   **Searching:** [TopCoder](https://www.topcoder.com/community/data-science/data-science-tutorials/binary-search/), [GeeksForGeeks](http://www.geeksforgeeks.org/searching-algorithms/)

+   **Sorting:** [TopCoder](https://www.topcoder.com/community/data-science/data-science-tutorials/sorting/), [GeeksForGeeks](http://www.geeksforgeeks.org/sorting-algorithms/)

+   **Divide & Conquer:** [GeeksForGeeks](http://www.geeksforgeeks.org/category/divide-and-conquer/)

+   **Number Theory:** [TopCoder - 1](https://www.topcoder.com/community/data-science/data-science-tutorials/prime-numbers-factorization-and-euler-function/), [TopCoder - 2](https://www.topcoder.com/community/data-science/data-science-tutorials/primality-testing-non-deterministic-algorithms/), [GeeksForGeeks](http://www.geeksforgeeks.org/number-theory-competitive-programming/)

+   **Graph Theory:** [TopCoder](https://www.topcoder.com/community/data-science/data-science-tutorials/introduction-to-graphs-and-their-data-structures-section-1/), [GeeksForGeeks](http://www.geeksforgeeks.org/graph-data-structure-and-algorithms/)

+   **Geometry:** [TopCoder](https://www.topcoder.com/community/data-science/data-science-tutorials/geometry-concepts-basic-concepts/)

+   **Dynamic Programming:** [TopCoder](https://www.topcoder.com/community/data-science/data-science-tutorials/dynamic-programming-from-novice-to-advanced/), [GeeksForGeeks](http://www.geeksforgeeks.org/dynamic-programming/)

+   **Game Theory:** [TopCoder](https://www.topcoder.com/community/data-science/data-science-tutorials/algorithm-games/)

+   **Basic Data Structures:** [TopCoder](https://www.topcoder.com/community/data-science/data-science-tutorials/data-structures/), [GeeksForGeeks](http://www.geeksforgeeks.org/data-structures/)

+   **Segment Tree:** [HackerEarth](https://www.hackerearth.com/practice/notes/segment-tree-and-lazy-propagation/), [CodeExtractor's Blog ;)](https://codeextractor.wordpress.com/2016/07/11/playing-with-ranges-segment-tree/)

---

# Some Pro Tips 

Following are few points that one can make use of in order to get better at Competitive programming--

+   Get yourself familiar with well-known algorithms and data structures. Read tutorials, watch video lectures and try to implement them in your own way.

+   PRACTICE is the mantra to being a better programmer. Practice problems on SPOJ, Codeforces, Codechef or any other judge whenever you find time. Ignore doing problems that are easy for you, instead do those problems which are challenging for you.

+   Don't just do problems using algorithm but instead understand how the given algorithm works and you'll be able to modify it according to the question's requirements.

+   Do read the editorials after the contest is over. Try to understand the approach of those problems that you were unable to do during the contest. After that, try solving them. It'll help you understand new concepts and their implementation.

+   There's no harm in seeing other's code after the contest as long as you are not doing *copy-paste*. You'll learn how to implement codes in simple and elegant way.

+   It's ok to spend hours on coming up with an approach to a problem. But, if you are stuck for too long, discuss the problem with friends and within your groups. Someone might have already done the problem or might help you in coming up with an approach.

+   Most importantly, you need to be persistent and keep on going and you'll soon be a pro :). 

---

# Resources for Further Reading

+   [https://discuss.codechef.com/questions/48877/data-structures-and-algorithms](https://discuss.codechef.com/questions/48877/data-structures-and-algorithms)

+   [https://discuss.codechef.com/questions/18752/what-are-the-must-known-algorithms-for-online-programming-contests](https://discuss.codechef.com/questions/18752/what-are-the-must-known-algorithms-for-online-programming-contests)

+   [https://www.quora.com/What-are-the-algorithms-required-to-solve-all-problems-using-C%2B%2B-in-any-competitive-coding-contest/answer/Amit-Rai-6?share=2cd036da&srid=LrGv](https://www.quora.com/What-are-the-algorithms-required-to-solve-all-problems-using-C%2B%2B-in-any-competitive-coding-contest/answer/Amit-Rai-6?share=2cd036da&srid=LrGv)

+   [https://www.quora.com/Can-anyone-provide-me-a-list-of-all-algorithms-needed-for-ACM-ICPC/answer/Utpal-Kumar-Jha?share=857ba537&srid=LrGv](https://www.quora.com/Can-anyone-provide-me-a-list-of-all-algorithms-needed-for-ACM-ICPC/answer/Utpal-Kumar-Jha?share=857ba537&srid=LrGv)

+   [https://www.quora.com/Competitive-Programming/What-was-Anudeep-Nekkantis-Competitive-Programming-strategy-to-become-35th-in-Global-ranking-in-just-6-7-months](https://www.quora.com/Competitive-Programming/What-was-Anudeep-Nekkantis-Competitive-Programming-strategy-to-become-35th-in-Global-ranking-in-just-6-7-months)

+   [https://www.quora.com/ACM-International-Collegiate-Programming-Contest-ICPC/For-an-ACM-ICPC-beginner-how-should-I-start](https://www.quora.com/ACM-International-Collegiate-Programming-Contest-ICPC/For-an-ACM-ICPC-beginner-how-should-I-start)