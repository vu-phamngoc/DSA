```
#include <stdio.h>
int main() {
    int n,x;
    int c=0;
    double s=0;
    scanf("%d",&n);
    
    while(n--){
        scanf("%d",&x);
        if(x>=0)s+=x,c++;
    }
    printf("%.3f",s/c);
    
}
```