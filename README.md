# kth Smallest element in a BST
## https://leetcode.com/problems/kth-smallest-element-in-a-bst

Given a binary search tree, write a function kthSmallest to find the kth smallest element in it.

**Note: You may assume k is always valid, 1 ≤ k ≤ BST's total elements.**
```
Example 1:

Input: root = [3,1,4,null,2], k = 1
   3
  / \
 1   4
  \
   2
Output: 1

Example 2:

Input: root = [5,3,6,2,4,null,null,1], k = 3
       5
      / \
     3   6
    / \
   2   4
  /
 1
Output: 3
```

Follow up:
What if the BST is modified (insert/delete operations) often and you need to find the kth smallest frequently? How would you optimize the kthSmallest routine?

## Implementation :

```java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
class Solution {
    public int kthSmallest(TreeNode root, int k) {
        List<Integer> list = new ArrayList<>();
        inorderTraversal(root, list);
        return list.get(k-1);
    }
    
    public void inorderTraversal(TreeNode node, List<Integer> list){
        if(node != null){
            inorderTraversal(node.left, list);
            list.add(node.val);
            inorderTraversal(node.right, list);
        }
    }
}
```

# References :
https://www.youtube.com/watch?v=C6r1fDKAW_o
