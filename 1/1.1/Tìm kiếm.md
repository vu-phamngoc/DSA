# Tìm kiếm
```
#include <stdio.h>
int main() {
    int n,k,a;
    int kq=-1;
    scanf("%d",&n);
    scanf("%d",&k);
    for(int i=1;i<=n;i++){
    scanf("%d",&a);
    
    if(a==k)
        kq=i;
    }
    printf("%d",kq);
    return 0;
}


```
