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