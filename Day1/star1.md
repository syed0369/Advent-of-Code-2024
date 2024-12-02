## Solution
Sort and take difference of corresponding elements

## Code
```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int i;
    vector<int> a(1000), b(1000);
    freopen("stdin.txt", "r", stdin);
    long long sum = 0;
    for(i = 0; i < 1000; i++) {
        cin >> a[i] >> b[i];
    }

    sort(a.begin(), a.end());
    sort(b.begin(), b.end());

    for(i = 0; i < 1000; i++) {
        sum += abs(a[i] - b[i]);
    }
    cout << sum;
    return 0;
}
```
