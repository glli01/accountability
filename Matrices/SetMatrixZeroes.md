# Set Matrix Zeroes no. 73
  
## **Problem description:**   
Given an m x n integer matrix matrix, if an element is 0, set its entire row and column to 0's, and return the matrix.

You must do it in place.
**Given:**  
vector<vector<int>> matrix, an m x n matrix that you are trying to set zeroes correctly in.
  
  
## Problem Link: https://leetcode.com/problems/set-matrix-zeroes/solution/
## **Solution:**  
  The way that I did it was quite simple and not exactly in place.  I made two vectors, cols, and rows, to track which rows and cols needed to be set as zeroes. I chose to do this because the original, easy algorithm of whenever you find a zero you set the entire row and column to zero would not work because when you arrived in the next iteration of checks, in the next row or next col, you would find one of the set zeroes, resulting in you setting more zeroes than you were supposed to.  
  The O(1) space solution was quite different than how I did it.  Instead of brute forcing it like I did (which was very simple), it was much smarter.  You set the beginning row and cols as flags to tell whether the row or column needs to be set as zeroes.  Thus you iterate through the matrix and when you find a matrix[i][j] == 0 , you set matrix[i][0] = 0 and matrix[0][j] = 0. and continue from where you left off.  After you are done iterating through the array only the first row and column should have been changed.  Now you just set all the rows and columns that have a 0 in their first index to all 0's, an edge case to this is [0][0] because it would just erase all of your hardwork if you read that first so you start at first row and first column to avoid this and then save [0][0] for last.
