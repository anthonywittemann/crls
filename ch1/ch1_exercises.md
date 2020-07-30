# CRLS Algorithms Chapter 1 Exercises

1.1-1
Give a real-world example that requires sorting or a real-world example that re- quires computing a convex hull.
```
Sorting: Prioritizing tasks to be completed. You have a bunch of files and you need to sort by last modified.
Convex Hull: A Robot that needs to figure out how to grip an object it is trying to manipulate or pick up.
```

1.1-2
Other than speed, what other measures of efficiency might one use in a real-world setting?
```
memory (RAM and Disk) usage, Interpretability/simplicity
```


1.1-3
Select a data structure that you have seen previously, and discuss its strengths and limitations.
```
Array: 
- good for storing ordered data and performing vectorized operations
- bad when data is sparse and unordered
```


1.1-4
How are the shortest-path and traveling-salesman problems given above similar? How are they different?
```
Both have a defined starting and ending point but intermediate path is not clear. Both have combinatorially many possible solutions. 
The TSP has to visit multiple nodes along a path, but when finding the shortest path there's no constraint on the nodes that make up that path. 
```


1.1-5
Come up with a real-world problem in which only the best solution will do. Then come up with one in which a solution that is “approximately” the best is good enough.
```
Best Solution - Solution to Proof of Work Puzzle (SHA-256 Hash matching)
Approximate Solution - Multiperiod Portfolio Optimization, Inventory Management and Optimal Execution of Trades on a Limit Order Book subject to time and fee constraints
```

1.2-1
Give an example of an application that requires algorithmic content at the applica- tion level, and discuss the function of the algorithms involved.
```
Rendering a scene in a video game. The algorithms determine the RGB (and alpha) values at each time t, simulate the physics of the world.
```

1.2-2
Suppose we are comparing implementations of insertion sort and merge sort on the same machine. For inputs of size n, insertion sort runs in 8n^2 steps, while merge sort runs in 64n lg n steps. For which values of n does insertion sort beat merge sort?
```
8*n^2 = 64 * n * lg n      --> n^2 = 8 * n * lg n      --> n = 8 * ln n   --> n = 43.5593...
n < 44  values for which insertion sort is faster than merge sort
```

1.2-3
What is the smallest value of n such that an algorithm whose running time is 100n^2 runs faster than an algorithm whose running time is 2^n on the same machine?
```
100 * n^2 = 2^n   --> n = 14.3247...
n > 14  values for which algorithm with running time 100n^2 runs faster than algorithm with runtime 2^n
```
