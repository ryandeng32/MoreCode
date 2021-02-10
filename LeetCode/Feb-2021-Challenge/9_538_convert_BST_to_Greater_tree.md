[Link to the Problem](https://leetcode.com/problems/convert-bst-to-greater-tree/)
### My initial solution 
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    # I didn't know a better solution, so I traversed the tree's value into an array
    # and then manipulated the array and reassigned values to the tree 
    # Space: O(n) 
    # Time: O(n^2) 
    def convertBST(self, root: TreeNode) -> TreeNode:
        val = [] 
        if root is None: 
            return None 
            
        def traverse(node): 
            if node.left: 
                traverse(node.left)
            val.append(node.val) 
            if node.right: 
                traverse(node.right)
        traverse(root) 
     
        for i in range(len(val)-1): 
            val[i] += sum(val[i+1:])
            
        def apply(node): 
            if node.left: 
                apply(node.left) 
            node.val = val[0]
            val.pop(0) 
            if node.right: 
                apply(node.right) 
        apply(root) 
        return root 
```

A better solution is to reverse-traverse a tree
```python
class Solution(object):
    def __init__(self):
        self.total = 0

    def convertBST(self, root):
        if root is not None:
            self.convertBST(root.right)
            self.total += root.val
            root.val = self.total
            self.convertBST(root.left)
        return root
```
