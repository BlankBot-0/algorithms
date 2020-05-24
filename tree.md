#tree

+ [Symmetric Tree](#symmetric-tree)
+ [Maximum Depth of Binary Tree](#maximum-depth-of-binary-tree)
+ [Same Tree](#same-tree)
+ [Invert Binary Tree](#invert-binary-tree)
+ [Path Sum](#path-sum)
+ [Subtree of Another Tree](#subtree-of-another-tree)

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
## Invert Binary Tree

https://leetcode.com/problems/invert-binary-tree/

```python
def invertTree(self, root: TreeNode) -> TreeNode:
    if not root:
        return None
    root.left, root.right = root.right, root.left
    self.invertTree(root.left)
    self.invertTree(root.right)
    return root

```
## Path Sum

https://leetcode.com/problems/path-sum/

```python
def hasPathSum(self, root: TreeNode, sum: int) -> bool:
    if not root:
        return False
    sum -= root.val
    if not root.left and not root.right and sum == 0:
        return True
    return self.hasPathSum(root.left, sum) or \
        self.hasPathSum(root.right, sum)

```
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