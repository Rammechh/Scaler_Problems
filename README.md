<!--ts-->
Problems
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
     * Pairs with Given Difference
  + [Day56_Hashing1](#day56_Hashing1)
     * Sub-array with 0 sum
     * Longest Consecutive Sequence
     * Shaggy and Distance
  + [Day58_Hashing2](#day58_Hashing2)
     * Count Rectangles
     * Replicating Substring
     * Count Right Triangles
     * Points on same line
  + [Day59_String_Algorithms](#day59_String_Algorithms)
     * Boring substring
  + [Day61_Stacks](#Day61_Stacks)
     * Count Rectangles
     * Sort stack using another stack
     * Passing game
     * Task Scheduling
     * Double Character Trouble
  + [Day62_Stacks2](#Day62_Stacks2)
     * Double Character Trouble
     * Evaluate Expression
  + [Day63_Queues](#Day63_Queues)
     * Task Scheduling
     * First non-repeating character


   


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
### 2) Pairs with Given Difference
  + i, j = 0, 1 while (i< n && j < n): find diff and add those pair in set
  + len(set) will give ans

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
### S1)1) Replicating Substring
  + Take Counter of given string. check if all values in Counter % A == 0, if not return -1
### 1) Points on same line
  + Refer attached doc (not practised)
### 2) Count Right Triangles
  + Try fixing each point as the intersection of perpendicular and base and try finding other points. Once it is fixed, for the other two points, one point will share the same x-coordinate and the other point will share the same y-coordinate with the selected point. For points sharing same x or y coordinate we can use map to store the points.
  + Mx and My are the maps (a= Mx[A[i]] & b= My[B[i]] ) Count += (a-1) * (b-1) will fetch the ans
### 3) Count Rectangles
 + Run two loops by fixing the two diagonally opposite ends of the rectangle. We have fixed the one diagonal of the rectangle and two corner points, from this we can easily find the other two points of the rectangle.
 + Suppose we have two diagonally opposite points: (x1, y1) and (x2, y2). Then the other two points of the rectangle must be (x1, y2) and (x2, y1).
 + We just have to check if these two points (x1, y2) and (x2, y1) are given or not. If present increment the answer.
 + For every rectangle, we have incremented the answer twice because every rectangle has two diagonals. So, our real answer will be half of the answer obtained after running two loops.

Day59_String_Algorithms
================
### Boring substring
  + No specific knowledge is requires to solve this question you just need to observe and find an existing pattern hidden in the parities of ASCII value of characters.
  + ‘a’ must be present near ‘c’ ,similarly ‘c’ must be near ‘e’ as we can see odd characters can be put aside each other and there will be no boring substring in it.
  + Like: “acegik…” No boring substring present in this string. Similarly for even characters.
  + Now just traverse in the string and form two strings one containing the odd characters and other even characters.
  + Sort both of them and check if placing them together doesn’t make a boring substring at their join point.
  + For example: A = “abcdefg” So , odd = “aceg” even= “bdf”
  + Check the string s= odd+even or s=even+odd doesn’t contain any boring substring. Time Complexity : O(A)

Day61_Stacks
================
### 1) Min Stack
 + push(x) -- Push element x onto stack. pop() -- Removes the element on top of the stack. top() -- Get the top element. getMin() -- Retrieve the minimum element in the stack.(refer attached)
### 2) Sort stack using another stack
  + Create a temporary stack say B. While input stack is not empty: 1. pop an element from input stack calls it x. 2. while the temporary stack is not empty and top of the temporary stack is greater than x pop from the temporary stack and push it into input stack. 3. push x in the temporary stack. The sorted numbers are in the temporary stack.
### 4) Passing game
  + Push the new id in the stack to keep track of the latest player who has the ball. Now you should pass the ball to the previous player who forwarded you the ball, so you can easily pop the last player from the stack.

Day62_Stacks2
================
### 2) Double Character Trouble
  + Consider an example string abba. When we remove the “bb”, the remaining string is “aa” which has to be removed as well. So we need to keep track of the characters before the first occurrence of similar consecutive characters. We can do this using a stack.
We keep pushing the characters in a stack, if the current character is equal to the top of the stack, we pop from the stack, since they represent a pair of similar characters.

### 3) Evaluate Expression
  + Arithmetic expression in Reverse Polish Notation i.e., 2 3 / . whenever you encounter a operator pop 2 operands from stack and append the result again to stack.

Day63_Queues
===============
### 1) Task Scheduling
  + Till find the B[i] element in A[0] pop element at front of A and add it at back of A and increase count by 1
### 3) First non-repeating character
  + You need to maintain map for each character of the stream. After that you can also maintain a queue for extraction of information. Each character is inserted and removed from queue atmost 1 time hence time complexity is O(n).
___________________________________________
for (auto c : A)
{
mp[c]++;
q.push(c);
while (!q.empty() && mp[q.front()] > 1) q.pop();
if (!q.empty()) ans.push_back(q.front());
else ans.push_back(‘#’);
}
____________________________________________
