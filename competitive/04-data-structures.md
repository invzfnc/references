#### Dynamic array, `vector`
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // declaration
    vector<int> v;
    
    // append element
    v.push_back(3);
    v.push_back(2);
    v.push_back(5);
    
    // pop last element
    v.pop_back();
    
    cout << "length: " << v.size() << endl; // 2
    cout << "last element: " << v.back() << endl; // 2

    // iterating
    for (auto x : v)
        cout << x << endl;
        
    // initialization
    vector<int> p(10); // length 10, initial value 0
    vector<int> q(10, 1); // length 10, initial value 1
    vector<int> r = {1, 2, 3, 4, 5};
}
```

#### Dynamic array, `string`
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    string s = "ha";
    
    cout << s + s << endl; // haha
    s = s + s + ";";
    cout << s << endl; // haha;
    
    s[4] = '!'; // char only
    cout << s << endl; // haha!
    
    string c = s.substr(0, 4); // substr(start, length)
    cout << c << endl; // haha
    
    // find position of the first occurence of substring
    cout << s.find("!") << endl; // 4
}
```

#### `set`
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    set<int> s; // distinct
    
    s.insert(3);
    s.insert(4);
    s.insert(5);
    s.insert(3);
    
    for (auto x : s)
        cout << x << ", ";
    cout << endl;
    // 3, 4, 5,
    
    // returns number of occurence (0 or 1 in this case)
    cout << s.count(3) << endl; // 1
    
    // removes all instance of element specified
    s.erase(5);
    cout << s.count(5) << endl; // 0
}
```

#### `map`
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    map<string, int> m;
    
    m["monkey"] = 2;
    m["dog"] = 5;
    
    cout << m["dog"] << endl; // 5
    cout << m["cat"] << endl; // 0
    
    if (m.count("dog"))
        cout << "dog exists in map" << endl; // printed
        
    for (auto x : m)
        cout << x.first << ": " << x.second << endl;
    // cat: 0
    // dog: 5
    // monkey: 2
}
```

#### Built-in `sort`, `reverse`, `random_shuffle`
```cpp
// vectors (iterators as arguments)
sort(v.begin(), v.end());
reverse(v.begin(), v.end());
random_shuffle(v.begin(), v.end());

// arrays (pointers as arguments)
sort(a, a + n);
reverse(a, a + n);
random_shuffle(a, a + n);
```
