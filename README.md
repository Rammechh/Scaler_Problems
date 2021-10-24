<!--ts-->
Table of Contents
=================
  * [Day34_Recursion](#Day34_Recursion)
     * Combinations
     * Letter Phone
  * [Day56_Hashing1](#day56_Hashing1)
     * Sub-array with 0 sum
     * Longest Consecutive Sequence
<!--te-->

Day34_Recursion
=================
### 4) Combinations:
 + For every element, you have 2 options. 
 + You may either include the element in your subset or you will not include the element in your subset. Make the call for both the cases.Make sure the return array contain the combinations in sorted order.
### 1) Letter Phone
 + For every integer, you have 1 or 3 or 4 options. Try appending every letter in the option to the string and move forward. For digit 0 and 1: there is only one possibility. For digit 7 and 9: there are 4 possibility. For all others: there are 3 possibility.

Day56_Hashing1
=================
 ### 1) Sub-array with 0 sum
 + The idea is to iterate through the array and for every element A[i], calculate sum of elements form 0 to i (this can simply be done as sum += arr[i]). If the current sum has been seen before, then there is a zero sum array. Hashing is used to store the sum values, so that we can quickly store sum and find out whether the current sum is seen before or not.
 ### 4) Longest Consecutive Sequence
 + If curr -1 not in A it cannot be the start 
 + So, we can proceed and run a loop to check if consecutive curr + 1 in A
 + Inner loop runs only once for every element =>TC = O(n+n) = O(n)
