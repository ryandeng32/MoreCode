# My Initial Solution
```python
# this is using a specific case of two pointers: fast and slow pointers 
# Time: O(n) 
# Space: O(1)
def hasCycle(self, head: ListNode) -> bool:
    fast = head
    slow = head 
    while fast and fast.next: 
        fast = fast.next.next
        slow = slow.next 
        if fast == slow: 
            return True
    return False
```

The fast pointer move 2 times faster than the slow pointer, so if there exists a loop, these two pointers will meet eventually
