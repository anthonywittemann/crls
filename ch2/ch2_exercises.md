2.1-1
Using Figure 2.2 as a model, illustrate the operation of INSERTION-SORT on the array A = [31, 41, 59, 26, 41, 58]
1. A = [31, 41, 59, 26, 41, 58]
2. A = [31, 41, 59, 26, 41, 58]
3. A = [26, 31, 41, 59, 41, 58]
4. A = [26, 31, 41, 41, 59, 58]
5. A = [26, 31, 41, 41, 58, 59]

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