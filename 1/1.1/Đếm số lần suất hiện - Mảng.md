```
#include <stdio.h>
int main() {
    int n,u,a[100005];
    int dem=0;
    scanf("%d %d",&n,&u);
    for(int i=0;i<n;i++)
    scanf("%d",&a[i]);
    for(int i=0;i<n;i++)
    if(a[i] == u)
    dem++;
    printf("%d",dem);
    return 0;
}
```