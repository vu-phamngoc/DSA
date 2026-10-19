```
#include <stdio.h>
int main() {
    int v,n;
    int a[100005];
    scanf("%d %d",&n,&v);
    for(int i=0;i<n;i++)
    scanf("%d",&a[i]);
     for(int i=0;i<n;i++)
      if(i!=v-1)
    printf(" %d",a[i]);
    return 0;
}
```