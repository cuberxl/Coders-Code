```cpp
#include<bits/stdc++.h>

#define int unsigned long long

using namespace std;

const int N = 2e6 + 10;

int ull = 1;

inline int read()

{

int x = 0, c = getchar();

while (c < '0' || c > '9') c = getchar();

do x = x * 10 + (c ^ 48), c = getchar();

while (c >= '0' && c <= '9');

return x;

}

int a[N], bkt[N];

int main()

{

cin.tie(0) -> sync_with_stdio(0);

int n = read();

for (int i = 1; i <= n; i ++)

a[i] = read();

int ans = 0;

for (int k = 0; k < 30; k ++)//无 MEX 部分

{

int cnt = (1 + n) * n / 2, lst = 0;//cnt: 全集 lst: 连续 0 个数

for (int i = 1; i <= n; i ++)

{

if ((a[i] >> k) & 1)

{

cnt -= (lst + 1) * lst / 2;

lst = 0;

}

else

lst ++;

}

if (lst)

cnt -= (lst + 1) * lst / 2;

ans += (ull << k) * cnt;

}

for (int k = 0; k <= 21; k ++)

{

int now = ull << k, nb = now - 1;

int l = 1, r = 1;

int pos[N]; pos[n + 1] = 0;

int cnt = (1 + n) * n / 2, lst = 0;

  

}

return 0;

}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTg4Nzg0MzI4XX0=
-->