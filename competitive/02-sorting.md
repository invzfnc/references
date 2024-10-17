The efficient general sorting algorithms work in $O(n \log n)$ time.

#### Bubble sort, $O(n^2)$
```cpp
for (int i = 0; i < n; i++) {
    for (int j = 0; j < n-1; j++) {
        if (array[j] > array[j+1]) {
            swap(array[j], array[j+1]);
        }
    }
}
```