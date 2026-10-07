# Xoá phần tử ở cuối danh sách liên kết đơn
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

struct Node* deleteEnd(struct Node* head) {
    if (head == NULL) return NULL;

    if (head->next == NULL) {
        free(head);
        return NULL;
    }

    struct Node* tmp = head;
    while (tmp->next->next != NULL) {
        tmp = tmp->next;
    }

    free(tmp->next);
    tmp->next = NULL;
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
        head = deleteEnd(head);
    }
    printList(head);
    return 0;
}

```