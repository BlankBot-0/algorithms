#linked-list

+ [Middle of the Linked List](#middle-of-the-linked-list)

## Middle of the linked list

https://leetcode.com/problems/middle-of-the-linked-list/

```python
def middleNode(self, head: ListNode) -> ListNode:
    fast = head
    slow = head
    while fast and fast.next:
        fast = fast.next.next
        slow = slow.next
    return slow

```