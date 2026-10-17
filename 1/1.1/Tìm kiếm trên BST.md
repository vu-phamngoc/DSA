```
#include <stdio.h>
int n,k;
int a[100005];
int timkiem(int i){
    if(i >= n || a[i] == -1){
        return 0;
    }
    if(a[i] == k){
        return 1;
    }
    if(k < a[i]){
        return timkiem(2*i+1);
    }
    return timkiem(2*i+2);
}
int main() {
    scanf("%d %d",&n,&k );
    for(int i = 0; i < n; i++){
        scanf("%d", &a[i]);
    }
    printf("%d", timkiem(0));
    return 0;
}
```
