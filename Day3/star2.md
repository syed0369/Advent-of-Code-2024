## Solution
Check for patterns do and don't also maintain a boolean value to check which was the most recent pattern.

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
        // Only this if statement is added to toggle start
        if(c == 'd') {
            cin >> c;
            if(c == 'o') {
                cin >> c;
                start = true;
                if(c == 'n') {
                    cin >> c;
                    if(c == '\'') {
                        cin >> c;
                        if(c == 't') {
                            start = false;
                        }
                    }
                }
            }
        }
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
