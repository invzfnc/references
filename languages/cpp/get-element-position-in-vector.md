```cpp
#include <iostream>
#include <algorithm>
#include <vector>

using namespace std;

int main()
{
    vector<int> nums = {5, 4, 3, 2, 1};
    auto it = find(nums.begin(), nums.end(), 7);
    if (it == nums.end()) 
        cout << "element not in vector" << endl;
    else {
        int position = it - nums.begin();
        cout << position << endl;
    }
    return 0;
}
```