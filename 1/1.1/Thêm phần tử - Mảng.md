```
#include<stdio.h>
int main()
{
    int n, p, v;
    scanf("%d %d %d",&n,&p,&v);
    int a[n];
    for(int i=0;i<n;i++){
        scanf("%d",&a[i]);
    }
    for(int i=0;i<n;i++){
        if(i==p-1){
            printf("%d ",v);
        }
        printf("%d ",a[i]);
    }
    return 0;
}
```