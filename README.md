ingly Linked List – Insert and Delete at Beginning (C)

This project demonstrates how to perform insertion and deletion at the beginning of a singly linked list using the C programming language.

📖 Description

The program:

Defines a Node structure

Inserts nodes at the beginning of the linked list

Deletes a node from the beginning

Displays the linked list before and after deletion

This example helps in understanding:

Dynamic memory allocation (malloc, free)

Pointer to pointer (struct Node** head)

Basic linked list operations

⚙️ Operations Implemented
🔹 1. Insert at Beginning

Steps:

Create a new node.

Assign data to the new node.

Make the new node point to the current head.

Update head to the new node.

⏱ Time Complexity: O(1)

🔹 2. Delete at Beginning

Steps:

Check if list is empty.

Store current head in a temporary pointer.

Move head to the next node.

Free the old head node.

⏱ Time Complexity: O(1)

🖥️ Program Code
#include <stdio.h>
#include <stdlib.h>

// Definition of a node
struct Node {
    int data;
    struct Node* next;
};

// Function to insert a node at the beginning
void insertAtBeginning(struct Node** head, int data) {
    struct Node* newNode = (struct Node*) malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = *head;
    *head = newNode;
}

// Function to delete a node from the beginning
void deleteAtBeginning(struct Node** head) {
    if (*head == NULL) {
        printf("List is empty!\n");
        return;
    }

    struct Node* temp = *head;
    *head = (*head)->next;
    free(temp);
}

// Function to print the list
void printList(struct Node* head) {
    while (head != NULL) {
        printf("%d -> ", head->data);
        head = head->next;
    }
    printf("NULL\n");
}

// Main function
int main() {
    struct Node* head = NULL;

    // Insert nodes at the beginning
    insertAtBeginning(&head, 10);
    insertAtBeginning(&head, 20);
    insertAtBeginning(&head, 30);

    printf("List before deletion: ");
    printList(head);

    // Delete node from beginning
    deleteAtBeginning(&head);

    printf("List after deletion: ");
    printList(head);

    return 0;
}
▶️ How to Run
Step 1: Compile the program
gcc linkedlist.c -o linkedlist
Step 2: Run the program
./linkedlist
📝 Sample Output
List before deletion: 30 -> 20 -> 10 -> NULL
List after deletion: 20 -> 10 -> NULL
🎯 Features

Modular functions

Dynamic memory management

Handles empty list condition

Beginner-friendly implementation

📚 Author

Ritik Chauhan

If you want, I can also create:

🔹 Menu-driven linked list program

🔹 Insert/Delete at end

🔹 Insert at specific position

🔹 Full Data Structures mini project README 🚀
