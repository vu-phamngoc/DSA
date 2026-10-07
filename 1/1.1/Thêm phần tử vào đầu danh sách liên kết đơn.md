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

void printList(struct Node* head) {
    struct Node* tmp = head;
    while (tmp != NULL) {
        printf("%d", tmp->data);
        if (tmp->next != NULL)
        printf(" ");
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
        head = addToFront(head, value);
    }
    printList(head);
    return 0;
}
```
