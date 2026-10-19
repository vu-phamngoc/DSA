```
#include <stdio.h>
int main() {
    int a,n,max;
    scanf("%d",&n);
    scanf("%d",&max);
    for(int i=0;i<n;i++)
    {
        scanf("%d",&a);
        if(a>max)
        max=a;
    }
    printf("%d",max);
}

```