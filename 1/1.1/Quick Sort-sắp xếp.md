# Partition Hoare
```
#include <stdio.h>
int partition(int a[], int l, int r) {
    int pivot = a[(l + r) / 2];
    int i = l, j = r;

    while (i <= j) {
        while (a[i] < pivot)
            i++;

        while (a[j] > pivot)
            j--;

        if (i <= j) {
            int t = a[i];
            a[i] = a[j];
            a[j] = t;
            i++;
            j--;
        }
    }

    return i;
}

void quickSort(int a[], int l, int r) {
    if (l < r) {
        int p = partition(a, l, r);
        quickSort(a, l, p - 1);
        quickSort(a, p, r);
    }
}

int main() {
    int n, a[10000000];
    scanf("%d", &n);

    for (int i = 0; i < n; i++)
        scanf("%d", &a[i]);

    quickSort(a, 0, n - 1);

    for (int i = 0; i < n; i++)
        printf("%d ", a[i]);

    return 0;
}

```
# Partition Lomutu
```
#include <stdio.h>

int partition(int a[], int l, int r) {
    int pivot = a[r];
    int i = l - 1;

    for (int j = l; j < r; j++) {
        if (a[j] <= pivot) {
            i++;
            int t = a[i];
            a[i] = a[j];
            a[j] = t;
        }
    }

    int t = a[i + 1];
    a[i + 1] = a[r];
    a[r] = t;

    return i + 1;
}

void quickSort(int a[], int l, int r) {
    if (l < r) {
        int p = partition(a, l, r);
        quickSort(a, l, p - 1);
        quickSort(a, p + 1, r);
    }
}

int main() {
    int n, a[10000000];
    scanf("%d", &n);

    for (int i = 0; i < n; i++)
        scanf("%d", &a[i]);

    quickSort(a, 0, n - 1);

    for (int i = 0; i < n; i++)
        printf("%d ", a[i]);

    return 0;
}

```
# Selection sort
```
#include <stdio.h>
int main() {
    int n,a[1000007];
    scanf("%d",&n);
    for(int i=0;i<n;i++){
        scanf("%d",&a[i]);
    }
    for(int i=0;i<n-1;i++){
    for(int j=1+i;j<n;j++){
    if(a[i]>a[j]){
        int tmp=a[i];
        a[i]=a[j];
        a[j]=tmp;
    }
    }
    }
    for(int i=0;i<n;i++){
        printf("%d ",a[i]);
    }
    return 0;
}
```