```
#include <stdio.h>
int main() {
    int n, s = 0;
    long long x, a[100000];
scanf("%d", &n);
    for (int i = 0; i < n; i++) {
        scanf("%lld", &x);
        if (x > 0) 
        a[s++] = x;
    }
if (s == 0)
        printf("ko co phan tu duong");
    else {
        printf("%d\n", s);
        for (int i = 0; i < s; i++)
        printf("%lld ", a[i]);
    }
    return 0;
}

```