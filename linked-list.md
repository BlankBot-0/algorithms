#linked-list

+ [Reverse linked list](#reverse-linked-list)
+ [Middle of the Linked List](#middle-of-the-linked-list)
+ [Palindrome Linked List](#palindrome-linked-list)

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