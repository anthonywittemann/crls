# CRLS Algorithms Chapter 1 Problems

1-1 Comparison of running times
For each function f(n) and time t in the following table, determine the largest size n of a problem that can be solved in time t, assuming that the algorithm to solve the problem takes f(n) microseconds.
|        | 1 seconds | 1 minute (60 s) | 1 hour (3600 s) | 1 day (86400 s) | 1 month (2,629,800 s) | 1 year (31,557,600 s) | 1 century (3,155,760,000 s) |
|--------|  :----:   |   :----:        |   :----:        |   :----:        |   :----:              |   :----:              |   :----:                    |
| lg n   |           |     n*2^60      |  n*2^3600       |   n*2^8640      |      n*2^2629800      |    n*2^31557600       |     n*2^3155760000          |
| sqrt n |           |   n*60^2 = 3600 |  n*3660^2       |  n*86400^2      |     n*2629800^2       |    n*31557600^2       |     n*3155760000^2          |
| n      |           |   n*60          |    n*3600       |     n*86400     |      n*2629800        |   n*31557600          |     n*3155760000            |
| n lg n |           |   n*60/5.907    |  n*3600/11.814  |    n*5268       |      n*123311         |   n*1266789           |     n*10^8                  |
| n^2    |           |   n*7           |    n*60         |    n*293        |      n*1621           |     n*5617            |      n*56176                |
| n^3    |           |   n*3           |    n*11         |    n*44         |      n*138            |     n*316             |      n*1479                 |
| 2^n    |           |   n*5           |    n*11         |    n*16         |      n*21             |     n*24              |      n*31                   |
| n!     |           |   n*4           |    n*6          |    n*8          |      n*9              |     n*10              |      n*12                   |
