## Solution
Check for pattern mul(\d{n},\d{m}) where 1 <= n, m <= 3.

## Code
```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    char c, c1, c2;
    freopen("stdin.txt", "r", stdin);
    int n1, n2;
    long long sum = 0;
    bool start = true;
    n1 = n2 = 0;
    while(cin >> c) {
        if(start && c == 'm') {
            cin >> c1 >> c2;
            if(c1 == 'u' && c2 == 'l') {
                cin >> c;
                if(c == '(') {
                    cin >> c;
                    while(n1 < 1000 && (c >= '0' && c <= '9')) {
                        n1 = n1 * 10 + c - '0';
                        cin >> c;
                    }
                    if(c == ',') {
                        cin >> c;
                        while(n2 < 1000 && (c >= '0' && c <= '9')) {
                            n2 = n2 * 10 + c - '0';
                            cin >> c;
                        }
                    }
                    if(c == ')') {
                        sum += n1 * n2;
                    }
                    n1 = n2 = 0;
                }
            }
        }
    }
    cout << sum << "\n";
    return 0;
}

```
