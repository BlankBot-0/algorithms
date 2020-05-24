#tree

+ [Same Tree](#same-tree)

## Same Tree

https://leetcode.com/problems/same-tree/

```python
def isSameTree(self, p: TreeNode, q: TreeNode) -> bool:
    if not p and not q:
        return True
    if not p or not q or p.val != q.val:
        return False
    isLeftSame = self.isSameTree(p.left, q.left)
    isRightSame = self.isSameTree(p.right, q.right)
    return isLeftSame and isRightSame

```