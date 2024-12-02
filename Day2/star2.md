## Solution
Check by deleting each element and see if it satisfies the constraint.

## Code
```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int i, j, count = 0;
    string s;
    int n;
    freopen("stdin.txt", "r", stdin);
    
    while(getline(cin, s)) {
        s = s + " ";
        n = 0;
        vector<int> v;
        for(i = 0; i < s.length(); i++) {
            if(s[i] == ' ') {
                v.push_back(n);
                n = 0;
            }
            else {
                n = 10 * n + s[i] - '0';
            }
        }
        for(j = 0; j < v.size(); j++) {
            int ele = v[j];
            v.erase(v.begin() + j);
            bool increasing, decreasing;
            increasing = decreasing = true;
            for(i = 0; i < v.size() - 1; i++) {
                increasing &= (v[i] < v[i + 1] && v[i + 1] - v[i] <= 3);
                decreasing &= (v[i] > v[i + 1] && v[i] - v[i + 1] <= 3);
                if(!(increasing || decreasing))
                    break;
            }
            v.insert(v.begin() + j, ele);
            if(i == v.size() - 2) {
                count++;
                break;
            }
        }
    }
    cout << count << "\n";
}

```
