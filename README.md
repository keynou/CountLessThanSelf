Suppose we are given an integer array nums and want to return a new counts
array. The counts array has the property where counts[i] is the number of
smaller elements to the right of nums[i].

Example:

Input: [5,2,6,1]

Output: [2,1,1,0]

Explanation:

To the right of 5 there are 2 smaller elements (2 and 1).
To the right of 2 there is only 1 smaller element (1).
To the right of 6 there is 1 smaller element (1).
To the right of 1 there is 0 smaller element.

-------------------------------------------------------------
Solution:
I solved this problem with the help of a helper data structure: AVL Trees.
So, the core idea is to make the initial array into a pair of its value and
its index: vec.push_back(make_pair(nums[i],i))
Then sort this vector based on its first number. Then, start from the
beginning of this vector and insert things into the AVL tree for the indexes
and update the height and nodes on the left and nodes on the right for the
tree and update the relevant nodes in the tree after eash insertion. This
will take log n for the tree to complete. Also we will search for the node
that we just inserted and we count the number of nodes on the right of each
node, since those were smaller nodes that were added before the current node
and should be counted as the answer for that node. And then just put the
number into the index that we just entered to the tree.
What I want to show you in this code is:
1) I correctly identify the algorithm.
2) I use correct data structures and can manipulate them based on the needs.
3) I can define my own data structures.
4) The flow of the code I wrote is readable and understandable.