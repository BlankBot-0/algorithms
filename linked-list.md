#linked-list

+ [Remove Nth Node From End of List](#remove-nth-node-from-end-of-list)

## Remove Nth Node From End of List

https://leetcode.com/problems/remove-nth-node-from-end-of-list/

```python
def removeNthFromEnd(self, head: ListNode, n: int) -> ListNode:
    if not head.next:
        return None
    curr = head
    counter = 0
    while curr:
        curr = curr.next
        counter += 1

    nth = counter - n
    if nth == 0:
        return head.next
    curr = head

    for i in range(nth-1):
        curr = curr.next
    curr.next = curr.next.next
    return head

```