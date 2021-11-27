# Quick Sort
Perform Quick Sort using JAVA language.

# About Quick Sort
Quick sort is a highly efficient sorting algorithm and is based on partitioning of array of data into smaller arrays. A large array is partitioned into two arrays
one of which holds values smaller than the specified value, say pivot, based on which the partition is made and another array holds values greater than the pivot value.

Quicksort partitions an array and then calls itself recursively twice to sort the two resulting subarrays. This algorithm is quite efficient for large-sized data sets 
as its average and worst-case complexity are O(n2), respectively.

![quick_sort](https://user-images.githubusercontent.com/35636662/143672874-5afc9d77-ec5c-4a2e-9c0e-62d580e45c0c.gif)

# Java
   Step 1: choose the rightmost element as pivot
   
           int pivot = array[high];
  
  Step 2:
  
         // pointer for greater element
         int i = (low - 1);

         // traverse through all elements
         // compare each element with pivot
         for (int j = low; j < high; j++) {
         if (array[j] <= pivot) {
         // if element smaller than pivot is found
         // swap it with the greatr element pointed by i
         i++;
         // swapping element at i with element at j
         int temp = array[i];
         array[i] = array[j];
         array[j] = temp;
         }
         }
         
  Step 3: swapt the pivot element with the greater element specified by i
    
         int temp = array[i + 1];
         array[i + 1] = array[high];
         array[high] = temp;       
 
 Step 4:
 
        static void quickSort(int array[], int low, int high) {
        if (low < high) {
        // find pivot element such that
        // elements smaller than pivot are on the left
        // elements greater than pivot are on the right
        int pi = partition(array, low, high);
        // recursive call on the left of pivot
        quickSort(array, low, pi - 1);
        // recursive call on the right of pivot
        quickSort(array, pi + 1, high);
        }
        }
        
Step 5: call quicksort() on array data

        int numbers[] = {15, 2, 13, 4, 8, 10, 50, 40};
        Quicksort.quickSort(data, 0, size - 1);
        
Step 6: Now,Print sorted Array in Ascending Order by loop
   
            System.out.print("Sorted Array in Ascending Order: ");
            for (int i = 0; i < numbers.length; i++) {
            System.out.print(numbers[i] + " ");
            }        
