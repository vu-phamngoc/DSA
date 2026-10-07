# Xoá phần tử ở đầu danh sách liên kết đơn
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node* next;
};

struct Node* addToFront(struct Node* head, int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = head;
    return newNode;
}

struct Node* deleteFront(struct Node* head) {
    if (head == NULL) return NULL;
    struct Node* temp = head;
    head = head->next;
    free(temp);
    return head;
}

void printList(struct Node* head) {
    struct Node* tmp = head;
    while (tmp != NULL) {
        printf("%d ", tmp->data);
        tmp = tmp->next;
    }
}

int main() {
    int n, m;
    scanf("%d %d", &n, &m);
    struct Node* head = NULL;
    for (int i = 0; i < n; i++) {
        int value;
        scanf("%d", &value);
        head = addToFront(head, value);
    }
    for (int i = 0; i < m; i++) {
        head = deleteFront(head);
    }
    printList(head);
    return 0;
}

```
