#tree

+ [Path Sum](#path-sum)

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