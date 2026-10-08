### P1199
---
```cpp
#include <bits/stdc++.h>
using namespace std;
const int N = 5e2 + 10;
typedef pair<int,int> PII;
int a[N][N];
short st[N];
int find_max(int a[], int n)
{
    int ans = -1, pos;
    for (int i = 1; i <= n; i++)
    {
        if (a[i] > ans)
            ans = a[i], pos = i;
    }
    return pos;
}
int main()
{
    ios::sync_with_stdio(0);
    cin.tie(0); cout.tie(0);
    int n; cin >> n;
    for (int i = 1; i <= n; i++)
        for (int j = i + 1; j <= n; j++)
        {
            cin >> a[i][j];
            a[j][i] = a[i][j];
        }
    int max_row, maxn = -1;
    for (int i = 1; i <= n; i++)
    {
        int x = find_max(a[i], n);
        int t = a[i][x];
        a[i][x] = -1, st[x] = 2;
        x = find_max(a[i], n);
        if (a[i][x] > maxn)
            maxn = a[i][x], max_row = i;
        a[i][x] = t;
    }
    cout << 1 << '\n' << maxn;
    return 0;
}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTIzODc3NTgwNV19
-->