# Duyệt trung thứ tự
```
#include <stdio.h>
int a[100005];
void duyet(int i,int n){
    if(i>=n || a[i]== -1)
    return;
    duyet(2*i+1,n);
    printf("%d ",a[i]);
    duyet(2*i+2,n);
}
int main() {
    int n;
    scanf("%d ",&n);
    for(int i=0;i<n;i++){
        scanf("%d",&a[i]);
    }
    duyet(0,n);
    return 0;
}


```
