# Reorder List no. 143 
  
## **Problem description:**   
You are given the head of a singly linked-list. The list can be represented as:

L0 → L1 → … → Ln - 1 → Ln
Reorder the list to be on the following form:

L0 → Ln → L1 → Ln - 1 → L2 → Ln - 2 → …
You may not modify the values in the list's nodes. Only nodes themselves may be changed.

Merge all the linked-lists into one sorted linked-list and return it.
**Given:** ListNode* head, the head of the linked list.
  
  
## Problem Link: https://leetcode.com/problems/reorder-list/
## **Solution:**  
The solution to this problem was quite simple.  You first want to find the size of the list while traversing through it and push everything onto a stack (stacks are Last in first out, and are very useful for going in reverse order, think toposort).  Then once you find the size go through from the beginning and reconnect first node with first off stack, then set current to be current->next.  In future iterations, connect node off stack with current and then do the same.  This results in the order previously said because we are going L0 first and connecting to Ln then connecting Ln to L0 + 1, or L1, and popping and going back to LN-1.  Repeating this n/2 times gets you to the last node and ensures you everything is connected. At this point you want to set current->next = nullptr because this node should not point to anything.

