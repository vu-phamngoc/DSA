# Queue
```
#include <stdio.h>
#define max 500
int main() {
    int n , u , type;
    int a[max];
    int l =0 , r = -1 , count = 0;
    scanf("%d" , &n);
    for(int i = 0 ; i<n ; i++){
        scanf("%d" , &type);
        
        if(type ==1 ){
            if(count >0){
                if(l == max -1){
                    l = 0;
                }
                else {
                    l++;
                }
                count--;
            }
        }
        if(type ==2 ){
            scanf("%d" , &u);
            if(count <  max){
                if(r == max -1 ){
                    r = 0;
                }
                else{
                    r++;
                }
                a[r]=u;
                count++;
            }
        }
    }
    while(count>0){
        printf("%d " ,a[l]);
        if(l == max-1){
            l=0;
        }
        else{
            l++;
        }
        count--;
    }
    return 0;
}


```
