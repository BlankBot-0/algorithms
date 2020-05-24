#linked-list

+ [Reverse linked list](#reverse-linked-list)
+ [Middle of the Linked List](#middle-of-the-linked-list)
+ [Palindrome Linked List](#palindrome-linked-list)
+ [Merge Two Sorted Lists](#merge-two-sorted-lists)
+ [Remove Nth Node From End of List](#remove-nth-node-from-end-of-list)
+ [Linked List Cycle II](#linked-list-cycle-ii)

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
## Merge Two Sorted Lists

https://leetcode.com/problems/merge-two-sorted-lists/

```python
def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
    head = ListNode()
    ptr = head
    needed = 0
    while l1 or l2:
        if not l1:
            ptr.next = l2
            break
        elif not l2:
            ptr.next = l1
            break
        else:
            if l1.val < l2.val:
                needed = l1.val
                l1 = l1.next
            else:
                needed = l2.val
                l2 = l2.next
            node = ListNode(needed)
            ptr.next = node
            ptr = ptr.next
    return head.next

```
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
## Linked List Cycle II

https://leetcode.com/problems/linked-list-cycle-ii/

```python
def detectCycle(self, head: ListNode) -> ListNode:
    slow = head
    fast = head
    node = head
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
        if slow == fast:
            while node != slow:
                slow = slow.next
                node = node.next
            return node
    return None

```