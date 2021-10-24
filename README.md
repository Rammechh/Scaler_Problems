<!--ts-->
Table of Contents
=================
  * [Day34_Recursion](#Day34_Recursion)
  * [Day56_Hashing1](#day56_Hashing1)
     * Sub-array with 0 sum
<!--te-->

Day34_Recursion
=================
### 4) Combinations:
 + For every element, you have 2 options. 
 + You may either include the element in your subset or you will not include the element in your subset. Make the call for both the cases.Make sure the return array contain the combinations in sorted order.

Day56_Hashing1
=================
 ### 1) Sub-array with 0 sum
 + The idea is to iterate through the array and for every element A[i], calculate sum of elements form 0 to i (this can simply be done as sum += arr[i]). If the current sum has been seen before, then there is a zero sum array. Hashing is used to store the sum values, so that we can quickly store sum and find out whether the current sum is seen before or not.
 ### 2) 
