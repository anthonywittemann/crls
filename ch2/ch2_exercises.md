2.1-1
Using Figure 2.2 as a model, illustrate the operation of INSERTION-SORT on the array A = [31, 41, 59, 26, 41, 58]
1. A = [31, 41+, 59, 26, 41, 58]
2. A = [31, 41, 59+, 26, 41, 58]
3. A = [26, 31, 41, 59, 41+, 58]
4. A = [26, 31, 41, 41, 59, 58+]
5. A = [26, 31, 41, 41, 58, 59+]

2.1-2
Rewrite the INSERTION-SORT procedure to sort into nonincreasing instead of non- decreasing order.
```
for j = 2 to A.length
    key = A[j]􏰧
    i = j - 􏰵1
    while i > 0 and A[i] < key
        A[i + 1]􏰧 = A[i]
        i = i - 1
    A[i + 1] = key􏰧
```

2.1-3
Consider the searching problem:
Input: A sequence of n numbers A = [a1, a2, ..., an] and a value 􏰨v.
Output: An index i such that 􏰨v = A[i] or the special value NIL if 􏰨v does not
appear in A.
Write pseudocode for linear search, which scans through the sequence, looking for v. Using a loop invariant, prove that your algorithm is correct. Make sure that your loop invariant fulfills the three necessary properties.
```
def linear_search(A: List[int], v: int):
    idx = NIL
    for i in range(len(A)):
        if A[i] == v:
            idx = i
            break
    return idx
```


2.1-4
Consider the problem of adding two n-bit binary integers, stored in two n-element arrays A and B. The sum of the two integers should be stored in binary form in an (n+1)-element array C. State the problem formally and write pseudocode for adding the two integers.
```
def add_two_nbit_binary_ints(A: List[int], B: List[int]):
    bin_sum = [0 for _ in range(len(A) + 1)]
    carry = 0
    for i in range(len(A) - 1, -1, -1):  # iterate from least significant bit to most signficant bit
        if carry == 0:
            if A[i] == 1 and B[i] == 1:
                bin_sum[i + 1] = 0
                carry = 1
            elif (A[i] == 1 and B[i] == 0) or (A[i] == 0 and B[i] == 1):
                bin_sum[i + 1] = 1
                carry = 0
            else:
                bin_sum[i + 1] = 0
                carry = 0
        else:
            if A[i] == 1 and B[i] == 1:
                bin_sum[i + 1] = 1
                carry = 1
            elif (A[i] == 1 and B[i] == 0) or (A[i] == 0 and B[i] == 1):
                bin_sum[i + 1] = 0
                carry = 1
            else:
                bin_sum[i + 1] = 1
                carry = 0
    return bin_sum

```


2.2-1
Express the function n^3/1000 +􏰂 100n^2 􏰂+ 100n + 3 in terms of theta-n-notation.
```O(n^3)```

2.2-2
Consider sorting n numbers stored in array A by first finding the smallest element of A and exchanging it with the element in A[1]􏰃. Then find the second smallest element of A, and exchange it with A[2􏰃]. Continue in this manner for the first n elements of A. Write pseudocode for this algorithm, which is known as *selection sort*. What loop invariant does this algorithm maintain? Why does it need to run for only the first n elements, rather than for all n elements? Give the best-case and worst-case running times of selection sort in theta-n-notation.
```
def selection_sort(arr: list) -> list:
    def swap(i: int, j: int):
        arr[i], arr[j] = arr[j], arr[i]

    min, min_idx = -inf, -1
    for i in range(len(arr)):         # iterate over each element in the arr
        for j in range(i, len(arr)):  # find the min for the unsorted part of the arr
            if arr[j] < min:
                min, min_idx = arr[j], j
        swap(i, min_idx)

    return arr


Best case: O(n) 
Worst case: O(n^2)
```

2.2-3
Consider linear search again (see Exercise 2.1-3). How many elements of the input sequence need to be checked on the average, assuming that the element being searched for is equally likely to be any element in the array? How about in the worst case? What are the average-case and worst-case running times of linear search in theta-n-notation? Justify your answers.
```
avg # elements to be checked: n/2
worst case # elements to be checked: n
O(n) for both avg case and worst case
```

2.2-4
How can we modify almost any algorithm to have a good best-case running time?
```
Add a check at the beginning of the algorithm to see if the input already satisfies the desired output.
```

