#linked-list

+ [Remove Nth Node From End of List](#remove-nth-node-from-end-of-list)

## Remove Nth Node From End of List

https://leetcode.com/problems/remove-nth-node-from-end-of-list/

```python
def removeNthFromEnd(self, head: ListNode, n: int) -> ListNode:
    if not head.next:
        return None
    pointer = head
    preNth = head
    for _ in range(n):
        if not pointer.next:
            return head.next
        pointer = pointer.next
    while pointer.next:
        pointer = pointer.next
        preNth = preNth.next
    preNth.next = preNth.next.next
    return head

```