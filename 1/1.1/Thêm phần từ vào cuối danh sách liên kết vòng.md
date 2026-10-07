# Thêm phần từ vào cuối danh sách liên kết vòng

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

    if (head == NULL) {
        newNode->next = newNode;
        return newNode;
    }
    struct Node* tmp = head;
    while (tmp->next != head) {
        tmp = tmp->next;
    }
    tmp->next = newNode;
    newNode->next = head;
    return head;
}

void printCircularList(struct Node* head, int n) {
    if (head == NULL) return;

    struct Node* tmp = head;
    for (int i = 0; i < n; i++) {
        printf("%d", tmp->data);
        tmp = tmp->next;
        if (i < n - 1) printf(" ");
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
    printCircularList(head, n);
    return 0;
}

```