<!--ts-->
Problems
=================
  + [Day31_Maths_Prime_numbers](#Day31_Maths_Prime_numbers)
     * Lucky Numbers
  + [Day32_Maths_Combinatorics](#Day32_Maths_Combinatorics)
     * Sorted Permutation Rank with Repeats
     * Compute nCr % m
     * Compute nCr % p
     * Summation
  + [Day34_Recursion](#Day34_Recursion)
     * Combinations
     * Letter Phone
  + [Day35_BackTracking](#Day35_BackTracking)
     * Combination Sum II
     * Palindrome Partitioning
     * Word Break II
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
     * Nearest Smaller Element
     * Largest Rectangle in Histogram
  + [Day63_Queues](#Day63_Queues)
     * Task Scheduling
     * First non-repeating character
     * Perfect Numbers
  + [Day66_LinkedList2](#Day66_LinkedList2)
     * Palindrome List
  + [Day67_Trees](#Day67_Trees)
     * Level Order
     * Inorder Traversal (pending)
     * Vertical Order traversal (pending)
     * Binary Tree From Inorder And Postorder (pending)
  + [Day68_Trees2](#Day68_Trees2)
     * TOP VIEW
     * Balanced Binary Tree
     * Right view of Binary tree
  + [Day69_BST](#Day69_BST)
     * Kth Smallest Element In Tree
     * Valid Binary Search Tree
     * Sorted Array To Balanced BST
  + [Day72_Tries](#Day72_Tries)
     * Shortest Unique Prefix
     * Spelling Checker
     * Maximum XOR
     * 


<!--te-->
Day31_Maths_Prime_numbers
==================
### 2)Lucky Numbers
  + Store the divisors count using Sieve Algorithm (first calculate for prime or not, again create another array to store divisor count)
  + Iterate thro it and if divisor count == 2: Count +=1 
  + return Count T.C = O(n log n) [sieve]
  
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
  
### 2) Compute nCr % m
  + Use Dp Approach - If we calculate nCr by calculating factorial of each number and then doing n! / (r! * (n-r)!) % m. This will not work as the factorial can be very large and will cause overflow. As we know nCr = n-1Cr-1 + n-1Cr. So we will use Dynamic Programming approach and calculate the value of nCr.

### 3) Compute nCr % p
  + This problem can be solved using Fermat’s Little theorem. a^p = a (mod p) where p is a prime number. 
  + a^(p-1) = 1 (mod p) Multiply by a inverse on both sides 
  + a^(p-2) = a^(-1) (mod p).
  + Using the above result, nCr can be calulated as ( fact[n]%p ) * inversemodulo( fact[n-r] %p ) * inversemodulo( fact[r] %p ).

### 4) Summation
_____________________________________________
 (1+x)A = 1 + AC1 x + AC2 x2 + AC3 x3 + …. + xA 
 Differentiating w.r.t x both sides we get:
 A(1+x)(A-1) = AC1 + 2AC2 x + 3AC3 x2 +…. + AxA-1
 Differentiating w.r.t x again both sides we get:
 A(A-1)(1+x)A-2 = 2AC2 + 6 AC3 x + …. + A(A-1)xA-2
 Putting x=2 we get:
 A(A-1)3A-2 = 2AC2 + 12AC3+…. + A(A-1)3A-2
 So the right term is what we have to find so just calculate:
 A(A-1)3A-2 using modulo exponentiation and multiplication.
___________________________________________________

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

### Palindrome Partitioning
  + We can use recursion to generate all possible palindrome partitioning of s. When on index i, you incrementally check all substring starting from i for being palindromic. If found, you recursively solve the problem for the remaining string and add it to your solution. Start this recursion from starting position of the string.

### Word Break 2
  + You start exploring every substring from the start of the string, and check if its in the dictionary. If it is, then you check if it is possible to form rest of the string using the dictionary words. If yes, you append the current substring to all the substring possible from rest of the string. If none of the substrings qualify, then there are no sentences possible from this string. .
  
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
### 1) Largest Rectangle in Histogram
  + whenever we encounter a lower height we pop out from stack (h = A[stack.pop()] ) and width = i - stack[-1] -1 and cal the area continues still curr height greater than height stored in stack.
  + In each loop we add index of curr to stack and maintain Max = max(Max, area)
  + return Max
  + [Leetcode ans explanation](https://leetcode.com/problems/largest-rectangle-in-histogram/discuss/452612/Thinking-Process-for-Stack-Solution)

### 2) Double Character Trouble
  + Consider an example string abba. When we remove the “bb”, the remaining string is “aa” which has to be removed as well. So we need to keep track of the characters before the first occurrence of similar consecutive characters. We can do this using a stack.
We keep pushing the characters in a stack, if the current character is equal to the top of the stack, we pop from the stack, since they represent a pair of similar characters.

### 3) Evaluate Expression
  + Arithmetic expression in Reverse Polish Notation i.e., 2 3 / . whenever you encounter a operator pop 2 operands from stack and append the result again to stack.

### 4) Nearest Smaller Element
  + To find the nearest smallest element on the left, create a stack and check the curr element with the top of the stack. 
  + If top element of stack is larger pop out till you find smallest and store in ans. when we go right, if curr element small no need of tracking all elements to left of it.
  + return ans list

Day63_Queues
===============
### 1) Task Scheduling
  + Till find the B[i] element in A[0] pop element at front of A and add it at back of A and increase count by 1
  
### 2) Perfect Numbers
  + use Queue to generate the sequence 
  + But the trick is generate only the half of a number to reduce the space and time

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

Day66_LinkedList2
================
### 1) Palindrome List
  + Using fast and slow (2 pointer approach) find the mid element.
  + from mid to end reverse the linked list (rev)
  + if head.val != rev.val return -1 
  + else 1 (palindrome)

Day67_Trees
===============
### 1)Inorder Traversal (pending)
    
### 2) Binary Tree From Inorder And Postorder (pending)

### 3) Level Order
  + using dfs may not give the correct ans
  + use Bfs, Queues.
  + Add node to Queue, While Queue: n = len(Queue) ans.append(Queue.get(0)) for i in range(n) add left and right childs. return ans
  
### 4) Vertical Order traversal (pending)
 
Day68_Trees2
==================
### 1)Balanced Binary Tree
  + A tree is balanced if : 1) Left subtree is balanced 2) Right subtree is balanced 3) And the difference is height of left and right subtree is atmost 1. 
  + Note that depth of a tree can also be calculated recursively as max(depth(rightSubtree), depth(leftSubtree)) + 1.
  + use a global variable ans, traverse thro the end of Tree and check if any point in time  if abs(lt_dt - rt_dt) > 1: update ans = 0 and return
  + else: wo uisng global variable
  _____________________________________________________
            if abs(left[0] - right[0]) > 1:
                return (max(left[0], right[0])+1, 0)
            else:
                b = left[1] * right[1]
                return (max(left[0], right[0])+1, b)
  _____________________________________________________

### 2)TOP VIEW
  + Dont use dfs method as it always result in wrong ans
  + use Queues -> You need to return every node such that it is visible from the top. In other words, it should be the leftmost or the rightmost till that level. This can be found using a queue and a modification of the level order traversal algorithm. You may need to maintain the level of each node along with the nodes themselves.

### 3) Right view of Binary tree
  + For each level whenever you encounters the last node on that level append it to the answer. try to Modify the level order traversal of tree for this problem. You should finally append the rightmost node for each level of the given binary tree and return the vector of the same.
  + same as level order traversal but append only the right elements to ans
 
Day69_BST
==============
### 1) Sorted Array To Balanced BST
  + For a BST, all values lower than the root go in the left part of root, and all values higher go in the right part of the root. For the tree to be balanced, we will need to make sure we distribute the elements almost equally in left and right part. So we choose the mid part of the array as root and divide the elements around it .
  + if l <= r: mid = (l + r) // 2; root  = TreeNode(A[mid]); root.left = balanced(l, mid-1, A); root.right = balanced(mid+1, r, A); return root

### 2) Valid Binary Search Tree
  + Simply do inorder and store elements if elements in sorted order, it is Valid BST but O(N) space
  + In recursion: if root.val < Max and root.val > Min: l = check(root.left, Min, root.val) r = check(root.right,  root.val , Max) if l and r: return 1 (Since LST <= root < RST)
 
### 4) Kth Smallest Element In Tree
  + Can follow two approach iterative or recursion
  + Iterative: store curr elements in stack and find ans
  + if curr: add to stack and curr = curr.left
  + else: curr = stack.pop and k-= 1 if k == 0: return curr.val else: curr = curr.right
  + Recursion: 1) set a global variable k = given val, in inorder traversal k-=1 if k==0: return root.val 2) or store in ans array and return kth A[k-1] since inorder is sorted.

Day72_Tries
===============
### Shortest Unique Prefix
  + input: ["zebra", "dog", "duck", "dot"]
__________________________________________________________________________________________________________________________________________
Now we will build prefix tree and we will also store count of characters
                root
                /|
         (d, 3)/ |(z, 1)
              /  |
          Node1  Node2
           /|        \
     (o,2)/ |(u,1)    \(e,1)
         /  |          \
Now, for every leaf / word , we find the character nearest to the root with frequency as 1. 
The prefix that the path from root to this character corresponds to, is the representation of the word. 
__________________________________________________________________________________________________________________________________________

### Spelling Checker
  + To this in O(n), you will need a different data structure called tries. You can insert all dictionary strings in a trie and then try finding all given strings in the trie, each of those will take O(length) time. Thus you can do this without the additional log factor you get while working with sets.
  + def __init__(self, x):
        self.val = x
        self.map = {}
        self.isTerminated = False
        
### Maximum XOR
  + We will find the maximum XOR of ith element with the previous i-1 elements of the array. Do this for all i 1 to N and update the maximum XOR at eact step. First build bitwise trie of i-1 elements which means insert the bit representation(from right to left) of all i-1 elements into the trie.
  + For ex: Given 3 numbers with their bit representation: 6(00110) , 5(00101) and 23(10111) and we need to find the maximum xor of 2(00010) with these numbers. Insert 6(00110), 5(00101) and (10101). After inserting, Our trie will look like this. (using only 5 bits for example)

        -1(root)
       /   \
      0     1
     /     /
    0     0
     \     \ 
      1     1
    /   \    \
   0     1    1
    \   /      \
   (5)1 0(6)      1(23)
   + We want to find the maximum xor of 2(00010) with the numbers in the trie. Start traversing in the trie from root, At every node, there can be two possibilites:
1) If the 2(00010) has 1 at that bit, move to the left means towards elements having that bit 0.
2) If the 2(00010) has 0 at that bit, move to the right means towards elements having that bit 1.
Basically move in the direction of opposite bit to set that bit in our answer to one.
  + Algorithm:
  1) Convert numbers into binary form
  2) Add numbers into the trie one by one and compute the maximum XOR of a number to add with all previously inserted. Update maximum XOR at each step.
  3) Return the maximum XOR calculated.
At every i we are checking the maximum xor with all elements from 0 to i-1. Time complexity of this step is O(log(max_element in the array)).
We are doing this for every i 1 to N. Overall time complexity is O(Nlog(max_element in the array))
