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
     * Permutations of A in B
     * Anagrams
  + [Day59_String_Algorithms](#day59_String_Algorithms)
     * Boring substring
     * Closest Palindrome
  + [Day61_Stacks](#Day61_Stacks)
     * Count Rectangles
     * Sort stack using another stack
     * Passing game
     * Task Scheduling
     * Double Character Trouble
     * Balanced Paranthesis
     * Redundant Braces
  + [Day62_Stacks2](#Day62_Stacks2)
     * Double Character Trouble
     * Evaluate Expression
     * Nearest Smaller Element
     * Largest Rectangle in Histogram
     * Next Greater
  + [Day63_Queues](#Day63_Queues)
     * Task Scheduling
     * First non-repeating character
     * Perfect Numbers
   + [Day64_Linked_List](#Day64_Linked_List)
     * Middle element of linked list
     * Remove Duplicates from Sorted List
     * Swap List Nodes in pairs
     * Reverse Link List II
  + [Day66_LinkedList2](#Day66_LinkedList2)
     * Palindrome List
     * Merge Two Sorted Lists
     * Add Two Numbers as Lists
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
  + [Day70_LCA_and_Tree_Problems](#Day70_LCA_and_Tree_Problems)
     * Invert the Binary Tree
  + [Day71_Problems_of_Trees_2](#Day71_Problems_of_Trees_2)
     * Next Pointer Binary Tree
     * Recover Binary Search Tree
  + [Day72_Tries](#Day72_Tries)
     * Shortest Unique Prefix
     * Spelling Checker
     * Maximum XOR
  + [Day73_Heaps1](#Day73_Heaps1)
     * Magician and Chocolates
     * Product of 3
  + [Day74_Heaps2](#Day74_Heaps2)
     * Running Median
     * Ath largest element.
     * K Places Apart
   + [Day75_Greedy_Algorithms](#Day75_Greedy_Algorithms)
     * Distribute Candy
     * Assign Mice to Holes
  + [Day80_Intro_to_Dynamic_Programming](#Day80_Intro_to_Dynamic_Programming)
     * Fibonacci Number
     * Stairs
     * Let's Party
     * Max Sum Without Adjacent Elements
     * Minimum Number of Squares
   + [Day81_Dynamic_Programming2](#Day81_Dynamic_Programming2)
     * Longest Common Subsequence
     * Edit Distance


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
  + a^(p-2) = a^(-1) (mod p)
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
 A(A-1)3A-2 using modulo exponentiation and multiplication
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

### Permutations of A in B
 + first we can create a hash map of size 26 to count the frequency of each character in A.
 + create another hash map of size 26 to count the frequency of each character in the first window of size N (length of A) in B, then slide through all windows and when both hashes will be same we can say we found a permutation of A in B as a substring.

### Anagrams
 + Can mainitain a freq Array and store it in hMap as str(freq Aray) = [index] since list cant be used as key in dict.
 + or can sort each word and maintain in hash map (

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
 
### Count A
 + The number of all substrings is the number of all pairs of (not necessary distinct) characters.  There are n*(n-1)/2 pairs of distinct characters.  You also need to add the non-distinct pairs, which are n. 
 + So the total number is n * (n-1) / 2 + n = n * (n+1) / 2. Therefore calculate the number of a (n) in the given string

### Closest Palindrome
 + We apply our regular palindrome checking algorithm and keep counting the number of times a set of mirror indices has different characters.If at the end of processing, this count is greater than 1, then it can never be possible since we will have to change more than 1 characters to make it a palindrome. If the count is 1, answer is always yes.
 + A corner case that needs to be considered is the case when count is 0. If the count is 0 and the length of palindrome is even, then we cannot change exactly one character to make it a palindrome, we will have to change 2 mirror indices. But if the count is 0 and length is odd, then it is possible as we can change the middlemost character to anything.

Day61_Stacks
================
### 1) Min Stack
 + push(x) -- Push element x onto stack. pop() -- Removes the element on top of the stack. top() -- Get the top element. getMin() -- Retrieve the minimum element in the stack.(refer attached)
### 2) Sort stack using another stack
  + Create a temporary stack say B. While input stack is not empty: 1. pop an element from input stack calls it x. 2. while the temporary stack is not empty and top of the temporary stack is greater than x pop from the temporary stack and push it into input stack. 3. push x in the temporary stack. The sorted numbers are in the temporary stack.
### 4) Passing game
  + Push the new id in the stack to keep track of the latest player who has the ball. Now you should pass the ball to the previous player who forwarded you the ball, so you can easily pop the last player from the stack.
### Balanced Paranthesis
 + Store the opening brackets ('(', '{', '[') in stack. ]
 + whenever you find the closing bracket check if it matches stack[-1] else return 0

### Redundant Braces
 + If i get a opening bracket or any operator(+, -, /, *) append it to stack.
 + If any closing bracket encountered, check if stack[-1] euql to opening bracket return 1. since it don't contain an operator (reduntant brackets)

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
 
### Next Greater
 + Store the index in the stack while you encounter greater element pop it from stack and add new greater index in stack

Day63_Queues
===============
### 1) Task Scheduling
  + Till find the B[i] element in A[0] pop element at front of A and add it at back of A and increase count by 1
  
### 2) Perfect Numbers
  + use Queue to generate the sequence 
  + But the trick is generate only the half of a number to reduce the space and time

### 3) First non-repeating character
  + You need to maintain map for each character of the stream. After that you can also maintain a queue for extraction of information. Each character is inserted and removed from queue atmost 1 time hence time complexity is O(n).

<pre>
for (auto c : A)
{
mp[c]++;
q.push(c);
while (!q.empty() && mp[q.front()] > 1) q.pop();
if (!q.empty()) ans.push_back(q.front());
else ans.push_back(‘#’);
}
</pre>

Day64_Linked_List
=================
### 2) Middle element of linked list
 + One way is to traverse the whole linked list and calculate the length and then traverse half the length to find the middle element. We can do it in one traversal by maintaing a slow and fast pointer. Fast pointer moves twice as the slow pointer does. When the fast pointer is at the end of linked list, the slow pointer will point to middle element. Return the element at which the slow pointer points.

### 3) Remove Duplicates from Sorted List
 + Skip the node where head->next != NULL && head->val == head->next->val.

### Swap List Nodes in pairs
 + Method 1: Just swap the values in the 2 nodes. In most cases, this won’t be a permissible solution. Method 2: Move around the pointers.
 + curr.next = swap(curr.next, curr.next.next)

### Reverse Link List II
 + Traverse thro the given linked list and have First(before start <B), From(==B start point), To(==C end point), Last(To.next)
 + reverse from B->C (From -> To) and join
 + First.next = to, From.next = last
 + return head

Day66_LinkedList2
================
### 1) Palindrome List
  + Using fast and slow (2 pointer approach) find the mid element.
  + from mid to end reverse the linked list (rev)
  + if head.val != rev.val return -1 
  + else 1 (palindrome)

### Merge Two Sorted Lists
 + only need to do is modify the next pointers.Don't create new nodes. At every step, you choose the minumum of the current head X on the 2 lists, and modify your answer’s next pointer to X. You move the current pointer on the said list and the current answer.
 + Corner case, Make sure that at the end of the loop, when one of the list goes empty, you do include remaining elemnts from the second list into your answer.

### Add Two Numbers as Lists
 + This problem can be solved exactly like the naive addition is done, using the temporary sum and implementing a value that represent a carry over.
 + two edge cases, 1) The first list can be shorter than the second list. -> if None consider as 0. 2) It is possible that the answer has more digits than both the given integers. -> run while A or B or carry

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

Day70_LCA_and_Tree_Problems
=====================
### 2) Invert the Binary Tree
  + Think recursively.On every node, you need to invert the left and right subtree and then swap them
  
Day71_Problems_of_Trees_2
=====================
### 1) Recover Binary Search Tree
  + Only if we swap 2 elements it becomes bst, so follow inorder traversal, In 2 places in array A[i] will be greater than A[i+1] that will be the ans
  + for O(1) space 
_________________________________________________________________________________________________________________________
<pre>def inorder(root):
            if not root:
                return
            inorder(root.left)
			      # 2 times in inorder the val will be greater than prev val
            # so just check and update, if not first update first and second updated with wrong value at first
            # only left with one value if again same val greater than prev val second will be updated to correct val
            if self.prev:
                if self.prev > root.val:
                    if not self.first:
                        self.first = self.prev
                    self.second = root.val
            self.prev = root.val
            inorder(root.right)
</pre>
___________________________________________________________________________________________________________________________

### 3) Next Pointer Binary Tree
  + Breadth first approach to exploring a tree is based on the concept of the level of a node. The level of a node is its depth or distance from the root node. We process all the nodes on one level before moving on to the next one. We need to link all the nodes together which lie on the same level and the level order or the breadth first traversal gives us access to all such nodes.
  + Follow Level order traversal and point node.next = q[0] if i<n-1
     
Day72_Tries
===============
### 1) Shortest Unique Prefix
  + input: ["zebra", "dog", "duck", "dot"]
__________________________________________________________________________________________________________________________________________
Now we will build prefix tree and we will also store count of characters
<pre>								     
                root
                /|
         (d, 3)/ |(z, 1)
              /  |
          Node1  Node2
           /|        \
     (o,2)/ |(u,1)    \(e,1)
         /  |          \
</pre>
Now, for every leaf / word , we find the character nearest to the root with frequency as 1. 
The prefix that the path from root to this character corresponds to, is the representation of the word. 
__________________________________________________________________________________________________________________________________________

### 2) Spelling Checker
  + To this in O(n), you will need a different data structure called tries. You can insert all dictionary strings in a trie and then try finding all given strings in the trie, each of those will take O(length) time. Thus you can do this without the additional log factor you get while working with sets.
  + def __init__(self, x):
        self.val = x
        self.map = {}
        self.isTerminated = False
        
### 3) Maximum XOR
  + We will find the maximum XOR of ith element with the previous i-1 elements of the array. Do this for all i 1 to N and update the maximum XOR at eact step. First build bitwise trie of i-1 elements which means insert the bit representation(from right to left) of all i-1 elements into the trie.
  + For ex: Given 3 numbers with their bit representation: 6(00110) , 5(00101) and 23(10111) and we need to find the maximum xor of 2(00010) with these numbers. Insert 6(00110), 5(00101) and (10101). After inserting, Our trie will look like this. (using only 5 bits for example)
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

Day73_Heaps1
===============
### 3) Product of 3
  + Maintain a max heap and popout 3 elements and append the product in ans.
  + Again pushback the popped element so that we keep track of the max elements encountered till now.

### 4) Magician and Chocolates
  + Brute Force - for each time find max val of A and add it to result also change the max value to floor(max/2)  
  + Maintain a max heap - we need to maintain the current maximum size among all bags for every time t = 1, … , B and also updating the sizes of the bags. 

Day74_Heaps2
================
### 3) K Places Apart
  + Take the first B+1 elements in a list, finding the minimum of the list will give us the first B+1 element in the sorted array. Remove the smallest element from the list and add the (B+2)th element from the given array to the list. 
  + Now taking the minimum of the list will give us the second element in the sorted array as each element is <= B distance away from it’s sorted position.Proceed in the same way and keep on finding the minimum of B+1 elements. 
  + We can use priority_queue to implement the above solution. Each time we remove the minimum element from the queue and add the new element to the queue.
  + Time complexity of removing an element from the priority_queue will be O(log B) as the size of the queue is <= B+1 and we will remove all N elements from the queue one by one. So, overall time complexity will be O(NlogB).

### 4) Ath largest element
  + One solution is to use Min Heap of size k to store k largest numbers. The Kth highest element is always at root and can be found in O(1) time.
  + How to process a new number? Compare the new number value, X with root of heap. If X is smaller, then ignore it.Otherwise replace root with X and call heapify for the root of modified heap. Time complexity of adding new element and finding the Kth highest element is O(LogK). STL priority queue can be used to implement a heap directly.

### 5) Running Median
  + Brute Force: sort the array each time for n elements and find the median (TC = O(N2logN))
  + Maintain Max and Min heap and maintain the length of Min and Max heap
  + Get the top element from Max heap for each run
 
Day75_Greedy_Algorithms
====================
### 1) Distribute Candy
 + Greedy works here ( Think of a supportive proof as as assignment ). Start with the guy with the least rating. Obviously he will receive 1 candy. If he did recieve more than one candy, we could lower it to 1 as none of the neighbor have higher rating.
 + Now lets move to the one which is second least. If the least element is its neighbor, then it receives 2 candies, else we can get away with assigning it just one candy. 
 + We keep repeating the same process to arrive at optimal solution.

### Assign Mice to Holes
 + Sort both arrays and find the max difference each time and retur the max value

Day80_Intro_to_Dynamic_Programming
==================
### 1) Fibonacci Number
  + In python: from functools import lru_cache (@lru_cache(None) add on top of function using dp)
  + <pre> A simple approach is to use the recursive implementation of the recursive relation given.
For ex: Calculate 4th term.

			       fib(4)   
			     /        \     
			 fib(3)      fib(2)
			/    \       /    \     
		  fib(2)   fib(1)  fib(1) fib(0)
		  /     \
		fib(1) fib(0)
We can see that the 2nd term is calculated multiple times. If we try to find large Fibonacci numbers, there will be more and more repetitions that are bad.
Time complexity of above: T(n) = T(n-1) + T(n-2) is exponential.
To avoid this, try to store the term which is calculated once and before calculating any other term check if it is already calculated or not.
If we already have that term use that. This will save us a lot of repetitions. In this we are only calculating each term once, So, time complexity will be linear.

Approach 2
__________
We can easily generate the Fibonacci series iteratively in linear time. Initialise: fib[0] = 0, fib[1] = 1
for i from 2 to A.
    fib[i] = fib[i-1] + fib[i-2].
fib[A] will be our answer.
Try to write a solution without using any extra memory.
</pre>
  
### 2) Stairs
  + This is the most basic dynamic programming problem. We know that we can take 1 or 2 step at a time. So, to take n steps, we must have arrived at it immediately from n - 1 or n - 2th step. If we knew the number of ways to reach n-1 and n-2th step, our answer would be the summation of their number of ways.
  + At step 0 -> 1 way. Step 1 -> 1 way. Step 2 can be reached from step 0 or step 2 (since we need to take only 1 or 2 steps) so we can simply add f[n-1] + f[n-2]
 
### 3) Let's Party
  + Every person can either pair with another person or can remain single. Let us consider the kth person, he can either remain single or he can pair up with someone from [1, k-1]. So here recurrence relation is :
  + Number_of_ways(k-1) + (k-1) * Number_of_ways(k-2) and by using dynamic programming we can solve overlapping subproblems.
  + i.e. dp[i] = dp[i-1] + dp[i-2] * (i-1)

### 4) Minimum Number of Squares
 + It is always possible to represent a number N as sum of squares i.e.(1^1+1^1+1^1+…..+1^1, N times).
 + example 12 : List of perfect square numbers ≤12 is 1,4,9. 11+1 = 12, 8+4 = 12, 3+9 = 12. So to reach 12 we have 3 choices i.e. 11,8,3.
+ Similarly we will solve for these subproblems with base case as for N=0, ans=0 and for N=1, ans=1.
<pre>
if n <= 1, 
then return n 
Else
   countMinSquares(n) = min {1 + countMinSquares(n - i*i)} 
                       where i >= 1 and i*i <= n
We can easily transform this exponential solution to DP as below :
dp[0]=0,dp[1]=1; // base cases.
i : [2...N]
{
    dp[i]=i;
    for every x : x>=1 & x*x<=i
    {
        dp[i]=min(dp[i],1+dp[i-x*x]);
    }
}
Time Complexity : O(N*sqrt(N))
Space Complexity : O(N)
</pre>
 
### 5) Max Sum Without Adjacent Elements
  + V : 
1 |  2  |  3  | 4
2 |  3  |  4  | 5
  + We know that within a column, we can choose at max 1 element.  And choosing either of those elements is going to rule out choosing anything from the previous or next column.
  + This means that choosing V[0][i] or V[1][i] has identical bearing on the elements which are ruled out. So, instead we replace each column with a single element which is the max of V[0][i], V[1][i]. Now we have the list as : 2 3 4 5
  + Now we want to find maximum sum of values where no 2 values are adjacent. Now our recurrence relation will depend only on position i and, a "include_current_element" which will denote whether we picked last element or not.
  
Day81_Dynamic_Programming2
======================
### 1)Longest Common Subsequence
 + Suppose LCS[i][j] represents the longest common subsequence of A[1..i] and B[1..j]. A[1..i] represents first i characters of string A. A[1..j] represents first j characters of string B. For every i, j we have two conditions A[i] == B[j] or not. Divide the problem based on this condition.
 + Recursion relation to divide the problem into smaller sub problems can be written as:-

LCS(i, j) = maximum (LCS(i-1, j-1] + 1,       //if(A[i] = B[j])
                     LCS(A[i-1], B[j],
                     LCS(A[i], B[j-1] )
 + LCS[ len(A) ][ len(B) ] will be our answer.

Think about the time complexity of this solution. 

### 2) Edit Distance
 1) Insert S2’s first character and then solve the problem for remaining part of S2, and S1.
 2) Delete S1’s first character and trying to match S1’s remaining string with S2.
 3) Replace S1’s first character with S2’s first character in which case we solve the problem for remaining part of S1 and S2.
<pre>
int editDistance(string &S1, int index1, string &S2, int index2) {
// BASE CASES

if (S1[index1] == S2[index2]) {
     return editDistance(S1, index1 + 1, S2, index2 + 1);
} else {
     return min(
    1 + editDistance(S1, index1 + 1, S2, index2), // Delete S1 char
            1 + editDistance(S1, index1, S2, index2 + 1), // Insert S2 char
            1 + editDistance(S1, index1 + 1, S2, index2 + 1) // Replace S1 first char with S2 first char
     );
} }
</pre>
