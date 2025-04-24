# Assignment-4-java
 Write a Java program to sort an array of integers in ascending order using the Selection Sort algorithm. After each pass, print the array to show how the smallest element is selected and swapped.
public class SelectionSortDemo {

    // Method to perform Selection Sort
    public static void selectionSort(int[] arr) {
        int n = arr.length;

        // Outer loop for each pass
        for (int i = 0; i < n - 1; i++) {
            // Assume the minimum is the first unsorted element
            int minIndex = i;

            // Inner loop to find the smallest element in the unsorted part
            for (int j = i + 1; j < n; j++) {
                if (arr[j] < arr[minIndex]) {
                    minIndex = j;
                }
            }

            // Swap the found minimum element with the first unsorted element
            int temp = arr[minIndex];
            arr[minIndex] = arr[i];
            arr[i] = temp;

            // Print the array after each pass
            System.out.print("Pass " + (i + 1) + ": ");
            printArray(arr);
        }
    }

    // Helper method to print an array
    public static void printArray(int[] arr) {
        for (int value : arr) {
            System.out.print(value + " ");
        }
        System.out.println();
    }

    // Main method
    public static void main(String[] args) {
        int[] arr = {64, 25, 12, 22, 11};

        System.out.println("Original array:");
        printArray(arr);

        selectionSort(arr);

        System.out.println("Sorted array:");
        printArray(arr);
    }
}
