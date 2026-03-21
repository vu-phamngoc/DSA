```
#include <stdio.h>
int main() {
    int n, p, v;
    scanf("%d %d %d", &n, &p, &v);
    int a[n + 1];
    for (int i = 1; i <= n; i++) {
    scanf("%d", &a[i]);
    }
    for (int i = n; i >= p; i--) {
    a[i + 1] = a[i];
    }
    a[p] = v;
    for (int i = 1; i <= n + 1; i++) {
    printf("%d", a[i]);
    if (i < n + 1) printf(" ");
    }
    printf("\n");
    return 0;
}

```
