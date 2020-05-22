#linked-list

+[Reverse linked list](#reverse-linked-list)
+[Middle of the linked list](#middle-of-the-linked-list)
+[Palindrome linked list](#palindrome-linked-list)
+[Merge two sorted lists](#merge-two-sorted-lists)
+[Remove nth node from end of list](#remove-nth-node-from-end-of-list)
+[Linked list cycle II](#linked-list-cycle-ii)
+[Linked list cycle](#linked-list-cycle)

## Reverse linked list

https://leetcode.com/problems/reverse-linked-list/

'''python
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

'''

## Middle of the linked list

https://leetcode.com/problems/middle-of-the-linked-list/

'''python
#code
'''

## Palindrome linked list

https://leetcode.com/problems/palindrome-linked-list/

'''python
#code
'''

## Merge two sorted lists

https://leetcode.com/problems/merge-two-sorted-lists/

'''python
#code
'''

## Remove nth node from end of list

https://leetcode.com/problems/remove-nth-node-from-end-of-list/

'''python
#code
'''

## Linked list cycle II

https://leetcode.com/problems/linked-list-cycle-ii/

'''python
#code
'''

## Linked list cycle

https://leetcode.com/problems/linked-list-cycle/

'''python
#code
'''