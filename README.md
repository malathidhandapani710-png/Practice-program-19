class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class Solution:
    # Function to check if the linked list has a loop.
    def detectLoop(self, head):
        if not head:
            return False
            
        slow = head
        fast = head
        
        while fast and fast.next:
            # Slow moves 1 step
            slow = slow.next
            # Fast moves 2 steps
            fast = fast.next.next
            
            # If they meet, there is a loop
            if slow == fast:
                return True
                
        # If fast reaches the end, no loop
        return False
