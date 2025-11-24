# Ex20 Sorting an Array using Merge Sort Algorithm
## DATE: 10/10/2025
## AIM:
To design a program that sorts a given array of integers in ascending order without using built-in sorting functions, achieving O(n log n) time complexity and minimal space usage.
## Algorithm
1.Build a max heap by heapifying all non-leaf nodes from bottom to top.


2.Swap the first element (largest) with the last element of the heap.


3.Reduce the heap size by one.


4.Heapify again from the root to restore the max-heap structure.


5.Repeat until all elements are removed from the heap, producing a sorted array.

 

## Program:
```
/*
Program tosorts a given array of integers in ascending order without using built-in sorting functions
Developed by: NARRA RAMYA
RegisterNumber: 212223040128
import java.util.*;

public class Solution {
    
    private void swap(int[] arr, int index1, int index2) {
        int temp = arr[index1];
        arr[index1] = arr[index2];
        arr[index2] = temp;
    }

    // Heapify the subtree rooted at index i
    private void heapify(int[] arr, int n, int i) {
        int largest = i; 
        int left = 2 * i + 1;
        int right = 2 * i + 2; 

        if (left < n && arr[left] > arr[largest]) {
            largest = left;
        }

        if (right < n && arr[right] > arr[largest]) {
            largest = right;
        }

        if (largest != i) {
            swap(arr, i, largest); 
            heapify(arr, n, largest);
        }
    }

    private void heapSort(int[] arr) {
        int n = arr.length;
        for (int i = n / 2 - 1; i >= 0; i--) {
            heapify(arr, n, i);
        }

        for (int i = n - 1; i >= 0; i--) {
            swap(arr, 0, i);
            heapify(arr, i, 0);
        }
    }

    public int[] sortArray(int[] nums) {
        heapSort(nums);
        return nums;
    }

 
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Solution solution = new Solution();

        //System.out.println("Enter number of elements:");
        int n = sc.nextInt();
        
        int[] nums = new int[n];
        //System.out.println("Enter " + n + " elements:");
        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }

        int[] sorted = solution.sortArray(nums);
        System.out.println("Sorted array:");
        System.out.println(Arrays.toString(sorted));

        sc.close();
    }
}

*/
```

## Output:
<img width="744" height="261" alt="image" src="https://github.com/user-attachments/assets/fe74f3e0-ca23-452f-84e7-9873f11eaaee" />


## Result:
The program has been successfully implemented and executed.
It sorts the given array of integers in ascending order using the Merge Sort algorithm with a time complexity of O(n log n) and minimal extra space.
