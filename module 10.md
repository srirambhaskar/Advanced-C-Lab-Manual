## EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
# NAME:B SRI RAM
# REG NO:212223040203

# Aim:
To write a C program to search a given element in the given linked list.

# Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
# Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node *next;
};

void search(struct Node *head, char key) {
    struct Node *temp = head;
    int pos = 1, found = 0;
    while (temp != NULL) {
        if (temp->data == key) {
            printf("Element '%c' found at position %d\n", key, pos);
            found = 1;
            break;
        }
        temp = temp->next;
        pos++;
    }
    if (!found)
        printf("Element '%c' not found in the list\n", key);
}

int main() {
    struct Node *head = malloc(sizeof(struct Node));
    struct Node *second = malloc(sizeof(struct Node));
    struct Node *third = malloc(sizeof(struct Node));

    head->data = 'A';
    head->next = second;
    second->data = 'B';
    second->next = third;
    third->data = 'C';
    third->next = NULL;

    search(head, 'B');
    search(head, 'E');

    return 0;
}
```
# Output:

<img width="546" height="98" alt="image" src="https://github.com/user-attachments/assets/c1efe1d9-d00e-4754-bcd4-3891f6d202b5" />

# Result:
Thus, the program to search a given element in the given linked list is verified successfully.


## EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.

# Aim:
To write a C program to insert a node in a linked list.

# Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
# Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node *next;
};

void insert(struct Node **head, char value) {
    struct Node *newNode = malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;

    if (*head == NULL) {
        *head = newNode;
        return;
    }

    struct Node *temp = *head;
    while (temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
}

void display(struct Node *head) {
    while (head != NULL) {
        printf("%c -> ", head->data);
        head = head->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node *head = NULL;

    insert(&head, 'A');
    insert(&head, 'B');
    insert(&head, 'C');

    display(head);
    return 0;
}
```

# Output:

<img width="702" height="75" alt="image" src="https://github.com/user-attachments/assets/96a28dfc-c37b-4116-b751-58264137e292" />

# Result:
Thus, the program to insert a node in a linked list is verified successfully.


## EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST

# Aim:
To write a C program to traverse a doubly linked list.

# Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
# Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *prev;
    struct Node *next;
};

void traverse(struct Node *head) {
    struct Node *temp = head;
    printf("Doubly Linked List: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    struct Node *head = malloc(sizeof(struct Node));
    struct Node *second = malloc(sizeof(struct Node));
    struct Node *third = malloc(sizeof(struct Node));

    head->data = 10; head->prev = NULL; head->next = second;
    second->data = 20; second->prev = head; second->next = third;
    third->data = 30; third->prev = second; third->next = NULL;

    traverse(head);
    return 0;
}
```

# Output:

<img width="502" height="63" alt="image" src="https://github.com/user-attachments/assets/849f7e36-c89b-4bc6-ad7b-b55a920c9658" />

# Result:
Thus, the program to traverse a doubly linked list is verified successfully. 


## EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
# Aim:
To write a C program to insert an element in doubly linked list

# Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
# Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *prev;
    struct Node *next;
};

void insertEnd(struct Node **head, int value) {
    struct Node *newNode = malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;

    if (*head == NULL) {
        newNode->prev = NULL;
        *head = newNode;
        return;
    }

    struct Node *temp = *head;
    while (temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
    newNode->prev = temp;
}

void display(struct Node *head) {
    struct Node *temp = head;
    printf("Doubly Linked List: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    struct Node *head = NULL;

    insertEnd(&head, 10);
    insertEnd(&head, 20);
    insertEnd(&head, 30);

    display(head);
    return 0;
}
```

# Output:

<img width="533" height="68" alt="image" src="https://github.com/user-attachments/assets/75457eb8-3b22-4207-afb0-882c802ea089" />

# Result:
Thus, the program to insert an element in doubly linked list is verified successfully.


## EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST

# Aim:
To write a C function that deletes a given element from a linked list.

# Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.

# Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

void deleteElement(struct Node **head, int key) {
    struct Node *temp = *head, *prev = NULL;

    if (temp != NULL && temp->data == key) {
        *head = temp->next;
        free(temp);
        printf("Deleted element: %d\n", key);
        return;
    }

    while (temp != NULL && temp->data != key) {
        prev = temp;
        temp = temp->next;
    }

    if (temp == NULL) {
        printf("Element %d not found in the list\n", key);
        return;
    }

    prev->next = temp->next;
    free(temp);
    printf("Deleted element: %d\n", key);
}

void display(struct Node *head) {
    while (head != NULL) {
        printf("%d -> ", head->data);
        head = head->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node *head = malloc(sizeof(struct Node));
    struct Node *second = malloc(sizeof(struct Node));
    struct Node *third = malloc(sizeof(struct Node));

    head->data = 10; head->next = second;
    second->data = 20; second->next = third;
    third->data = 30; third->next = NULL;

    printf("Original List:\n");
    display(head);

    deleteElement(&head, 20);
    printf("After deletion:\n");
    display(head);

    return 0;
}
```

# Output:

<img width="609" height="165" alt="image" src="https://github.com/user-attachments/assets/c4cb2107-3936-4a1c-84c9-0588d21c87ec" />


# Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





