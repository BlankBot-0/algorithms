#tree

+ [Binary Tree Inorder Traversal](#binary-tree-inorder-traversal)

## Binary Tree Inorder Traversal

https://leetcode.com/problems/binary-tree-inorder-traversal/

```python
def inorderTraversal(self, root: TreeNode) -> List[int]:
    traversal = []
    stack, node = [], root
    while stack or node:
        if node:
            stack.append(node)
            node = node.left
        else:
            node = stack.pop()
            traversal.append(node.val)
            node = node.right
    return traversal

```