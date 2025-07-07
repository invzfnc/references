Selection sort works by repeatedly finding the smallest element from the unsorted sublist and swaps it with the leftmost unsorted element (puts in front).

Selection sort has $O(n^2)$ time complexity.

```java
public static void selectionSort(double[] list) {
	for (int i = 0; i < list.length - 1; i++) {
		// find smallest element
		int low = i;
		for (int j = i + 1; j < list.length; j++) {
			if (list[j] < list[low]) {
				low = j;
			}
		}
		
		// swap
		if (i != low) {
			double x = list[i];
			list[i] = list[low];
			list[low] = x;
		}
	}
}
```