# Remove Nth Node From End of Linked List No. 19
  
## **Problem description:**   
Given the head of a linked list, remove the nth node from the end of the list and return its head.
**Given:** head of linked list
  
  
## Problem Link: https://leetcode.com/problems/remove-nth-node-from-end-of-list/
## **Solution:** 
The solution was very simple.  Just do a one pass and store it in a vector, then use vctor.size() - n to find the removed one and corresponding indices to find previous and next.
Then you just connect and return head.  Another way of doing this would be to use multiple pointers.  Two pass is to simply use one pointer and go to the end to find size.
Then count until Size - n and set that as previous and Size - n + 1 and set as removed and then just reconnect pointers.  With one pass you need multiple pointers ensuring that
one pointer is always 2 behind the first pointer.  Once the first pointer reaches location size - n + 1, you just connect second pointer to next next.
