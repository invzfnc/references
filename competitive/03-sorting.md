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

#### Inversions
A pair of array elements that are in the wrong order / when $a < b$ and $array[a] > array[b]$  
Example: The array `{1, 2, 2, 6, 3, 5, 9, 8}` has three inversions: `(6, 3)`, `(6, 5)` and `(9, 8)`