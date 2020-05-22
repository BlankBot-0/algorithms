#linked-list

+ [Reverse linked list](#reverse-linked-list)
+ [Middle of the Linked List](#middle-of-the-linked-list)

## Reverse linked list

https://leetcode.com/problems/reverse-linked-list/

```python
def reverseList(self, head: ListNode) -> ListNode:
    if head is None:
        return head
    curr = head
    prev = None
    next = head.next
    while curr:
        next = curr.next
        curr.next = prev
        prev = curr
        curr = next
    return prev

```
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