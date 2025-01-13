<h1>
  <span class="headline">Selection Sort in Java</span>
  <span class="subhead">Selection Sort Implementation</span>
</h1>

**Learning objective:** By the end of this lesson, you'll be able to code a selection sort algorithm in Java.

## Selection sort demo
For this demo, lets consider an array of student scores that need to be sorted from lowest to highest for ranking.

```java
public class SelectionSort {

    // Method to perform Selection Sort
    public static void selectionSort(int[] scores) {
        int n = scores.length;

        for (int i = 0; i < n - 1; i++) {
            int minIndex = i; // Assume the current index is the smallest
            for (int j = i + 1; j < n; j++) {
                if (scores[j] < scores[minIndex]) {
                    minIndex = j; // Update minIndex if a smaller element is found
                }
            }
            // Swap the found minimum with the element at index i
            int temp = scores[minIndex];
            scores[minIndex] = scores[i];
            scores[i] = temp;
        }
    }

    // Main Method to Demonstrate the Algorithm
    public static void main(String[] args) {
        int[] examScores = {78, 92, 88, 64, 99, 71};

        System.out.println("Original Scores:");
        for (int score : examScores) {
            System.out.print(score + " ");
        }

        // Sorting using Selection Sort
        selectionSort(examScores);

        System.out.println("\n\nSorted Scores:");
        for (int score : examScores) {
            System.out.print(score + " ");
        }
    }
}
```