#tree

+ [Subtree of Another Tree](#subtree-of-another-tree)

## Subtree of Another Tree

https://leetcode.com/problems/subtree-of-another-tree/

```python
def isSubtree(self, s: TreeNode, t: TreeNode) -> bool:
    if not s and not t:
        return True
    if (not s and t) or (s and not t):
        return False
    if self.isSameTree(s, t):
        return True
    return self.isSubtree(s.left, t) or self.isSubtree(s.right, t)


def isSameTree(self, p: TreeNode, q: TreeNode) -> bool:
    if not p and not q:
        return True
    if not p or not q or p.val != q.val:
        return False
    isLeftSame = self.isSameTree(p.left, q.left)
    isRightSame = self.isSameTree(p.right, q.right)
    return isLeftSame and isRightSame

```