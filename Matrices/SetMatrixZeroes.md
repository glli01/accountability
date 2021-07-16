# Merge K Sorted Lists no. 23 
  
## **Problem description:**   
You are given an array of k linked-lists lists, each linked-list is sorted in ascending order.

Merge all the linked-lists into one sorted linked-list and return it.
**Given:** vector<ListNode*>, a vector of all the list heads.
  
  
## Problem Link: https://leetcode.com/problems/merge-k-sorted-lists/
## **Solution:**  
Key points: Remember to keep calm and collected and think first about what the parameters of the problem are.
In this case, the key parameters are that we are:  
- Working with sorted linked lists  
- Returning a sorted linked list  
From knowing that we are working with linked lists, we know that each node is connected to another by a next pointer.  Thus, for our final list we must ensure that starting from 
the beginning of the list, we must have the minimum node connected to the nextSmallest node and so on.  
  
Using this information, we can devolve this problem into simply using a leastNode pointer and nextSmallest pointer, connecting them when needed and iterating leastNode to leastNode->next when it is smaller than nextSmallest because we know that the only values that can be smaller than nextSmallest must lie on least's list.  This is because we are working with sorted lists (every list must have only nodes after it that are larger than the head, and thus no other list other than least can have a node smaller than nextSmallest (Least will have such a node if and only if a value val exists such that least->val + val < nextSmallest->val, still satisfying the sorted property of each list).  From this we can simply sort the nodes by checking the next minimum value and setting least to connect to it every time.  
  
This becomes slightly complicated when we realize we have more than one list, but it is still pretty simple.  You set temp to least->next, but instead of deciding to always use temp, we need to find the minimum of the remaining, non-considered heads.  If this minimum is less than temp->val, then we must use that as nextSmallest instead.  However, without storing temp we would lose access to it, so when this is true we set the head of temp's list (previously least) to be temp, so that it may be considered as one of the non-considered heads upon the next iteration.  
  
Finding the stopping point also proved difficult but you want to return when either nextSmallest doesn't exist, everything has been traversed, or when min is not found and temp is null, also meaning that everything has finished sorting as there are only nodes left possibly in the same order on the current track.
