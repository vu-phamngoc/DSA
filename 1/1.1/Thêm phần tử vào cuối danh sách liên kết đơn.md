# Thêm phần tử vào cuối danh sách liên kết đơn
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* addToEnd(struct Node* head, int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;

    if (head == NULL) {
        return newNode;
    }

    struct Node* tmp = head;
    while (tmp->next != NULL) {
        tmp = tmp->next;
    }

    tmp->next = newNode;
    return head;
}

void printList(struct Node* head) {
    struct Node* tmp = head;
    while (tmp != NULL) {
        printf("%d", tmp->data);
        if (tmp->next != NULL) printf(" ");
        tmp = tmp->next;
    }
}

int main() {
    int n;
    scanf("%d", &n);
    struct Node* head = NULL;
    for (int i = 0; i < n; i++) {
        int value;
        scanf("%d", &value);
        head = addToEnd(head, value);
    }
    printList(head);
    return 0;
}

```
