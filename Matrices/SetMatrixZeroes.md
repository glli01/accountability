# Set Matrix Zeroes no. 73
  
## **Problem description:**   
Given an m x n integer matrix matrix, if an element is 0, set its entire row and column to 0's, and return the matrix.

You must do it in place.
**Given:**  
vector<vector<int>> matrix, an m x n matrix that you are trying to set zeroes correctly in.
  
  
## Problem Link: https://leetcode.com/problems/set-matrix-zeroes/solution/
## **Solution:**  
  The way that I did it was quite simple and not exactly in place.  I made two vectors, cols, and rows, to track which rows and cols needed to be set as zeroes. I chose to do this because the original, easy algorithm of whenever you find a zero you set the entire row and column to zero would not work because when you arrived in the next iteration of checks, in the next row or next col, you would find one of the set zeroes, resulting in you setting more zeroes than you were supposed to.  
  The O(1) space solution was quite different than how I did it.  Instead of brute forcing it like I did (which was very simple), it was much smarter.  You set the beginning row and cols as flags to tell whether the row or column needs to be set as zeroes.  Thus you iterate through the matrix and when you find a matrix[i][j] == 0 , you set matrix[i][0] = 0 and matrix[0][j] = 0. and continue from where you left off.  After you are done iterating through the array only the first row and column should have been changed.  Since we don't want to check the first row and or first column because they will clear your progress, we start at matrix[1][1] and for each cell, matrix[i][j], check matrix[i][0] and matrix[0][j], if either of these are equal to zero you set the cell to zero.  At the end you simply check matrix[0][0], if this is true set 0th row and col to 0.
