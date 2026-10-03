# Increasing-Order-Search-Tree
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def increasingBST(self, root: TreeNode | None) -> TreeNode | None:
        r=[]
        def add(root,r):
            if root is None:
                return None
            add(root.left,r)
            r.append(root.val)
            add(root.right,r)
        add(root,r)
        d=TreeNode(0)
        temp=d
        for i in range(len(r)):
            temp.right=TreeNode(r[i])
            temp=temp.right
        return d.right
