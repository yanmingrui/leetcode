1. > step one: create two new linkedlist
								one to save odd nodes
								one to save enve nodes

2. > step two: traverse the linkedlist
										the odd-th node is added in odd linkedlist, vice versa

3. > step three: the tail of odd linkedlist point to the head of even linkedlist
```
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def oddEvenList(self, head):
        """
        :type head: ListNode
        :rtype: ListNode
        """
        odd = 0
        even = 0
        odd_nodes = odd_node = ListNode('#')
        even_nodes = even_node = ListNode('@')
        find = head
        while(find):
            odd_nodes.next = find
            odd_nodes = odd_nodes.next
            find = find.next
            even_nodes.next = find
            even_nodes = even_nodes.next
            if find:
                find = find.next
            else:
                break
        odd_nodes.next = even_node.next
        return odd_node.next
```
