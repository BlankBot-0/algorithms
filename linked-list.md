#linked-list

+ [Merge Two Sorted Lists](#merge-two-sorted-lists)

## Merge Two Sorted Lists

https://leetcode.com/problems/merge-two-sorted-lists/

```python
def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
    head = ListNode()
    ptr = head
    while l1 or l2:
        if not l1:
            ptr.next = l2
            break
        elif not l2:
            ptr.next = l1
            break
        else:
            if l1.val < l2.val:
                ptr.next = l1
                l1 = l1.next
            else:
                ptr.next = l2
                l2 = l2.next
            ptr = ptr.next
    return head.next

```