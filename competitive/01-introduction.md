**Dynamic programming**: Algorithmic problem is first broken down into sub-problems, the results are saved, and then the sub-problems are optimized to find the overall solution.

**Greedy algorithm**: Any algorithm that follows the problem-solving heuristic of making the locally optimal choice at each stage.

**Sliding window technique**: A method used to efficiently solve problems that involve defining a window or range in the input data (arrays or strings) and then moving that window across the data to perform some operation within the window.

**Maximum subarray sum problem**
```cpp
//#include <bits/stdc++.h>
#include <iostream>
#include <vector>

using namespace std;

void alg1(int *, int);
void alg2(int *, int);
void alg3(int *, int);

int main() {
    int n = 8;
    int arr[n] = {-1, 2, 4, -3, 5, 2, -5, 2};

    alg3(arr, n);
}

/* O(n^3) */
void alg1(int * arr, int n) {
    int best = 0;
    for (int a = 0; a < n; a++) {
        for (int b = a; b < n; b++) {
            int sum = 0;
            for (int k = a; k <= b; k++) {
                sum += arr[k];
            }
            best = max(best, sum);
        }
    }
    cout << best << "\n";
}

/* O(n^2) */
void alg2(int * arr, int n) {
    int best = 0;
    for (int a = 0; a < n; a++) {
        int sum = 0;
        for (int b = a; b < n; b++) {
            sum += arr[b];
            best = max(best, sum);
        }
    }
    cout << best << "\n";
}

/* Kadane's, O(n) */
void alg3(int * arr, int n) {
    int best = 0;
    int sum = 0;
    for (int k = 0; k < n; k++) {
        sum = max(arr[k], sum + arr[k]);
        best = max(sum, best);
    }
    cout << best << "\n";
}
```