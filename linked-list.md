#linked-list

+ [Palindrome Linked List](#palindrome-linked-list)

## Palindrome Linked List

https://leetcode.com/problems/palindrome-linked-list/


```python
def isPalindrome(self, head: ListNode) -> bool:
    if not head:
        return True
    slow, fast = head, head
    stack = []
    while fast and fast.next:
        stack.append(slow.val)
        slow = slow.next
        fast = fast.next.next
    if fast:
        slow = slow.next
    while slow and len(stack):
        if stack.pop() != slow.val:
            return False
        slow = slow.next
    return True

```
with reverseList:
```python
def isPalindrome(self, head: ListNode) -> bool:
    if not head:
        return True
    slow, fast = head, head
    while fast and fast.next:
        fast = fast.next.next
        slow = slow.next
    slow = self.reverseList(slow)
    if slow.val != head.val:
        return False
    while slow:
        if head.val != slow.val:
            return False
        head = head.next
        slow = slow.next
    return True


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