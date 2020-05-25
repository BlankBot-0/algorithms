#linked-list

+ [Reverse linked list](#reverse-linked-list)

## Reverse linked list

https://leetcode.com/problems/reverse-linked-list/

```python
def reverseList(self, head: ListNode) -> ListNode:
    if not head:
        return None
    curr = head
    prev = None
    while curr:
        next = curr.next
        curr.next = prev
        prev = curr
        curr = next
    return prev

```