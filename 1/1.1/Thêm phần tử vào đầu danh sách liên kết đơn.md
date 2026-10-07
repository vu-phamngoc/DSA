```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* addAfterOrFront(struct Node* head, int a, int b) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = a;
    newNode->next = NULL;

    if (head == NULL) {
        newNode->next = head;
        return newNode;
    }

    struct Node* tmp = head;

    while (tmp != NULL) {
        if (tmp->data == b) {
            newNode->next = tmp->next;
            tmp->next = newNode;
            return head;
        }
        tmp = tmp->next;
    }

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
        int a, b;
        scanf("%d %d", &a, &b);
        head = addAfterOrFront(head, a, b);
    }

    printList(head);
    return 0;
}
```
