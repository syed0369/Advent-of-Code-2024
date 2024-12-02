## Solution
Find first and last occurences of the element in sorted array. This gives the freq. Multiply with value.

## Code
```cpp
#include <bits/stdc++.h>
using namespace std;


int binarySearch(vector<int>& b, int ele) {
    return upper_bound(b.begin(), b.end(), ele) - lower_bound(b.begin(), b.end(), ele);
}

int main()
{
    int i;
    vector<int> a(1000), b(1000);
    freopen("stdin.txt", "r", stdin);
    long long sum = 0;
    for(i = 0; i < 1000; i++) {
        cin >> a[i] >> b[i];
    }

    sort(b.begin(), b.end());

    for(i = 0 ; i < 1000; i++) {
        int count = binarySearch(b, a[i]);
        sum += 1ll * a[i] * count;
    }

    cout << sum;
    return 0;
}

```
