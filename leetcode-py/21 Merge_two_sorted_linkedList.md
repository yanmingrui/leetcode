##recursive
```
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def mergeTwoLists(self, l1, l2):
        """
        :type l1: ListNode
        :type l2: ListNode
        :rtype: ListNode
        """
        A = l1
        B = l2
        result = new_list = ListNode('#')
        
        while(A and B):
            if A.val < B.val :
                new_list.next = A
                new_list = new_list.next
                A =  A.next
            else :
                new_list.next = B
                new_list = new_list.next
                B =  B.next
            
        if not A:
            new_list.next = B
        if not B:
            new_list.next = A
        return result.next
```
