# Merge Two Sorted Lists no. 21  
  
## **Problem description:**   
Merge two sorted linked lists and return it as a sorted list. The list should be made by splicing together the nodes of the first two lists.  
**Given:** l1 the head of linked list 1 and l2, the head of linked list 2.  
  
  
## Problem Link: https://leetcode.com/problems/merge-two-sorted-lists/submissions/
## **Solution:**  
The solution to this question was actually quite simple.  You needed to create a pointer to lesser, or the lesser of the two nodes currently in comparison and a pointer to greater, the greater node that is currently being compared.  Once you have these two we simply traverse lesser = lesser->next until lesser->next is greater than greater. At this point we connect lesser to greater, and set greater to lesser->next and lesser to greater (the old next node contains a greater value than the current greater node and thus we make this switch).  We want to do this until either lesser or greater are nullptrs.  If greater is a nullptr then you know that the previous lesser->next was nullptr so we got to the end of the lesser list.
