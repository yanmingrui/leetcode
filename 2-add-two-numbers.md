```
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def addTwoNumbers(self, l1, l2):
        """
        :type l1: ListNode
        :type l2: ListNode
        :rtype: ListNode
        """
        carry = 0
        number = 0
        A = l1
        B = l2
        
        res_list = new = ListNode("#")
        temp = new
        while(A and B):
            
            number = (A.val + B.val + carry) % 10
            carry = (A.val + B.val + carry) // 10
            new.next = ListNode(number)

            new = new.next
            A = A.next
            B = B.next
        if not (A or B):
            if carry:
                new.next = ListNode(carry)
            
        else:
            if A:
                A.val += carry
                new.next = A
                while(A.val > 9 and A):
                    A.val = A.val %10
                    carry = 1
                    
                    if A.next:
                        A.next.val += carry
                        A = A.next
                    else:
                        A.next = ListNode(1)
                        break  
            else:
                B.val += carry
                new.next = B 
                while(B.val > 9 and B):
                    B.val = B.val %10
                    carry = 1
                    
                    if B.next:
                        B.next.val += carry
                        B = B.next
                    else:
                        B.next = ListNode(1)
                        break  
        return res_list.next
            
            
        
```
