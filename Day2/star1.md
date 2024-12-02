## Solution
Check if the array is increasing or decreasing and diff is `<= 3`.

## Code
```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int i, count = 0;
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
        bool increasing, decreasing;
        increasing = decreasing = true;
        for(i = 0; i < v.size() - 1; i++) {
            increasing &= (v[i] < v[i + 1] && v[i + 1] - v[i] <= 3);
            decreasing &= (v[i] > v[i + 1] && v[i] - v[i + 1] <= 3);
            if(!(increasing || decreasing))
                break;
        }
        if(i == v.size() - 1)
            count++;
    }
    cout << count << "\n";
}

```