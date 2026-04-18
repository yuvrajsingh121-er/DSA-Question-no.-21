# DSA-Question-no.-21

## 📌 Project Overview
This repository contains a robust implementation of the *Binary Search* algorithm in Java. This project is part of my exploration into Data Structures and Algorithms (DSA) while pursuing my B.Tech in CS-AIML.

Binary Search is an efficient algorithm for finding an item from a sorted list of items. It works by repeatedly dividing in half the portion of the list that could contain the item until you've narrowed down the possible locations to just one.


## 🚀 How it Works
1. *Initialize*: Start with two pointers, start at 0 and end at the last index.
2. *Calculate Mid*: Find the middle element of the current range.
3. *Compare*:
   - If arr[mid] is the target, return the index.
   - If arr[mid] < target, discard the left half (start = mid + 1).
   - If arr[mid] > target, discard the right half (end = mid - 1).
4. *Repeat*: Continue until the target is found or pointers cross.

## 🛠 Code Snippet
In this implementation, I corrected the logic error where the end pointer was incorrectly incrementing, which would cause an infinite loop.

```java
public class Array {
    public static int binarySearch(int array[], int key) {
        int start = 0;
        int end = array.length - 1;

        while(start <= end) {
            int mid = start + (end - start) / 2;

            if(array[mid] == key) return mid;
            
            if(array[mid] < key) {
                start = mid + 1;
            } else {
                end = mid - 1; // Corrected logic
            }
        }
        return -1;
    }

    public static void main(String[] args) {
        int array[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
        int target = 8;
        int result = binarySearch(array, target);
        
        System.out.println("Target found at index: " + result);
    }
}
