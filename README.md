<!--ts-->
Table of Contents
=================
  + [Day32_Maths_Combinatorics](#Day32_Maths_Combinatorics)
     * Sorted Permutation Rank with Repeats
  + [Day34_Recursion](#Day34_Recursion)
     * Combinations
     * Letter Phone
  + [Day35_BackTracking](#Day35_BackTracking)
     * Combination Sum II
  + [Day55_TwoPointers](#Day55_TwoPointers)
     * Another Count Rectangles
  + [Day56_Hashing1](#day56_Hashing1)
     * Sub-array with 0 sum
     * Longest Consecutive Sequence
     * Shaggy and Distance
  + [Day58_Hashing2](#day58_Hashing2)
     * Count Rectangles
  + [Day61_Stacks](#Day61_Stacks)
     * Count Rectangles

   


<!--te-->

Day32_Maths_Combinatorics
=================
### 1)Sorted Permutation Rank with Repeats
 + Take counter of give string
 + for i -> n-1
   * take denominator count -> dem = 1 for k in counter.values(): dem * = factorial(k) // Since we divide by their fac of common characters in combinations, then reduce that counter value
   * Now, for every charc -> for j in counter.keys(): if ord(A[i]) > ord(j) (finding the smaller characters on right than the current one, since it will come before in order) 
letter rank += 1 
       * rank += (letter_rank * self.fact(n-i-1) // denominator)
   * return the rank after all pass

Day34_Recursion
=================
### 4) Combinations:
 + For every element, you have 2 options. 
 + You may either include the element in your subset or you will not include the element in your subset. Make the call for both the cases.Make sure the return array contain the combinations in sorted order.
### 1) Letter Phone
 + For every integer, you have 1 or 3 or 4 options. Try appending every letter in the option to the string and move forward. For digit 0 and 1: there is only one possibility. For digit 7 and 9: there are 4 possibility. For all others: there are 3 possibility.

Day35_BackTracking
================

### HW3) Combination Sum II
 + Sort the given array
 + Generate all combinations (Subsequence) 
 + Check if sum of generated subseq is equal to given sum and subseq not in ans (check for duplicates in return list)

Day55_TwoPointers
================

### 6) Another Count Rectangles
 + Since given array is in sorted order we multiply 1st and last element if ans < B then add all elements before that
 + if ans > B -> j-- 
 + if ans < B: i++

Day56_Hashing1
=================
 ### 1) Shaggy and Distance
 + Since we are checking for same element again we can use hashmap to check if element already in hashMap
 + else we update the key, value = ele, index
 + if present in hashMap we subtract the curr index with stored index (hashMap.get(ele))
 
 ### 2) Sub-array with 0 sum
 + The idea is to iterate through the array and for every element A[i], calculate sum of elements form 0 to i (this can simply be done as sum += arr[i]). If the current sum has been seen before, then there is a zero sum array. Hashing is used to store the sum values, so that we can quickly store sum and find out whether the current sum is seen before or not.
 
 ### 4) Longest Consecutive Sequence
 + If curr -1 not in A it cannot be the start 
 + So, we can proceed and run a loop to check if consecutive curr + 1 in A
 + Inner loop runs only once for every element =>TC = O(n+n) = O(n)

Day58_Hashing2
=================
### 3) Count Rectangles
 + Run two loops by fixing the two diagonally opposite ends of the rectangle. We have fixed the one diagonal of the rectangle and two corner points, from this we can easily find the other two points of the rectangle.
 + Suppose we have two diagonally opposite points: (x1, y1) and (x2, y2). Then the other two points of the rectangle must be (x1, y2) and (x2, y1).
 + We just have to check if these two points (x1, y2) and (x2, y1) are given or not. If present increment the answer.
 + For every rectangle, we have incremented the answer twice because every rectangle has two diagonals. So, our real answer will be half of the answer obtained after running two loops.
 
Day61_Stacks
================
### 1) Min Stack
 + push(x) -- Push element x onto stack. pop() -- Removes the element on top of the stack. top() -- Get the top element. getMin() -- Retrieve the minimum element in the stack.(refer attached)
