# Xoá phần tử ở giữa danh sách liên kết đơn
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

struct Node* deleteAfter(struct Node* head, int b) {
    struct Node* tmp = head;
    while (tmp != NULL) {
        if (tmp->data == b && tmp->next != NULL) {
            struct Node* temp = tmp->next;
            tmp->next = temp->next;
            free(temp);
            return head;
        }
        tmp = tmp->next;
    }
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
    int n, m;
    scanf("%d %d", &n, &m);

    struct Node* head = NULL;

    for (int i = 0; i < n; i++) {
        int value;
        scanf("%d", &value);
        head = addToFront(head, value);
    }

    for (int i = 0; i < m; i++) {
        int b;
        scanf("%d", &b);
        head = deleteAfter(head, b);
    }

    printList(head);
    return 0;
}

```