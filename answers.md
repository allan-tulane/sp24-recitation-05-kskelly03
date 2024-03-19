# CMPS 2200 Reciation 5
## Answers

**Name:**__Kevin Skelly________


Place all written answers from `recitation-05.md` here for easier grading.







- **1b.**
- Note, I had to change the sizes of n in order to prevent fixed-pivot and ssort from exceeding max recursion depth

With an un-shuffled (already sorted list)
|   n |   qsort-fixed-pivot |   qsort-random-pivot |   selection sort |
|-----|---------------------|----------------------|------------------|
|  10 |               0.017 |                0.012 |            0.063 |
|  50 |               0.134 |                0.053 |            0.264 |
| 100 |               0.539 |                0.122 |            0.691 |
| 200 |               2.201 |                0.228 |            4.614 |
| 500 |              14.511 |                0.589 |           75.380 |
| 800 |              34.403 |                0.974 |          167.108 |
With the Shuffled List
|   n |   qsort-fixed-pivot |   qsort-random-pivot |   selection sort |
|-----|---------------------|----------------------|------------------|
|  10 |               0.014 |                0.011 |            0.059 |
|  50 |               0.045 |                0.054 |            0.274 |
| 100 |               0.114 |                0.108 |            0.721 |
| 200 |               0.245 |                0.267 |           10.156 |
| 500 |               0.658 |                0.667 |           81.258 |
| 800 |               0.888 |                0.990 |          175.197 |

As you can see, the running times for random-pivot are significantly faster for an unshuffled list than the fixed-pivot, which is in turn significantly faster than selection sort. Fixed-pivot is comparably fast to random-pivot for a shuffled list, but selection sort remains the slowest. The change in fixed-pivot to random-pivot demonstrates how random-pivot will perform better asymptotically given anything besides the worst case, in which they will perform similarly. For fixed and random, the upper bound is O(nlogn) for the average case, with random performing better outside of worst case. Selection sort is O(n^2) in best case and worst case, which aligns with the results achieved above.

- **1c.**

|      n |   qsort-fixed-pivot |   qsort-random-pivot |   tim-sort |
|--------|---------------------|----------------------|------------|
|    100 |               0.115 |                0.119 |      0.022 |
|    200 |               0.216 |                0.238 |      0.022 |
|    500 |               0.558 |                0.635 |      0.050 |
|   1000 |               1.193 |                1.378 |      0.101 |
|   2000 |               2.518 |                2.612 |      0.197 |
|   5000 |               5.885 |                6.608 |      0.477 |
|  10000 |              10.907 |               11.802 |      0.887 |
|  20000 |              21.191 |               23.587 |      1.833 |
|  50000 |              58.103 |               62.218 |      5.044 |
| 100000 |             120.437 |              129.912 |     10.751 |

Python's implementation of timsort is significantly faster than the quicksort implementations we had