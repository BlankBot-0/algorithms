#tree

+ [Symmetric Tree](#symmetric-tree)
+ [Maximum Depth of Binary Tree](#maximum-depth-of-binary-tree)

## Symmetric Tree

https://leetcode.com/problems/symmetric-tree/

Recursively
```python
def isSymmetric(self, root: TreeNode) -> bool:
    if not root:
        return True
    return self.ismirror(root.left, root.right)

def ismirror(self, l, r):
    if l and r:
        return l.val == r.val and \
        self.ismirror(l.left, r.right) and \
        self.ismirror(l.right, r.left)
    return l == r
```
Iteratively
```python
def isSymmetric(self, root: TreeNode) -> bool:
    if not root:
        return True
    stack = [(root.left, root.right)]
    while stack:
        l, r = stack.pop()
        if not l and not r:
            continue
        if not l or not r:
            return False
        if l.val != r.val:
            return False
        stack.append((l.left, r.right))
        stack.append((l.right, r.left))
    return True
```
##Maximum Depth of Binary Tree

https://leetcode.com/problems/maximum-depth-of-binary-tree/

```python
def maxDepth(self, root: TreeNode) -> int:
    if not root:
        return 0
    return max(self.maxDepth(root.left), self.maxDepth(root.right)) + 1

```