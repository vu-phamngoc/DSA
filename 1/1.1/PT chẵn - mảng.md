```
#include <stdio.h>
int main() {
    int n;
    int a[100005];
    int d=0;
    scanf("%d",&n);
    for(int i=0;i<n;i++)
    {
    scanf("%d",&a[i]);
       if(a[i] % 2 == 0)
        d++;
    }
    printf(" %d",d);
    for(int i=0;i<n;i++)
    if(a[i] % 2 == 0)
    printf(" %d",a[i]);
}

```