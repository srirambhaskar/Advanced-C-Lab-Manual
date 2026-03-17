## EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

# NAME:B SRI RAM
# REG NO:212223040203

# Aim:
To write a C program to display stack elements using an array.

# Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
# Program:
```
#include <stdio.h>
#define SIZE 5

int stack[SIZE];
int top = -1;

void push(int value) {
    if (top == SIZE - 1)
        printf("Stack Overflow\n");
    else
        stack[++top] = value;
}

void display() {
    if (top == -1)
        printf("Stack is empty\n");
    else {
        printf("Stack elements are:\n");
        for (int i = top; i >= 0; i--)
            printf("%d\n", stack[i]);
    }
}

int main() {
    push(10);
    push(20);
    push(30);
    display();
    return 0;
}
```

# Output:

<img width="701" height="139" alt="image" src="https://github.com/user-attachments/assets/9803f169-645e-46be-80f6-12ea4d6ae5df" />

# Result:
Thus, the program to display stack elements using an array is verified successfully.
 

## EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.

# Aim:
To create a C program to push the given element in to a stack using array.

# Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
# Program:
```
#include <stdio.h>
#define SIZE 5

float stack[SIZE];
int top = -1;

void push(float value) {
    if (top == SIZE - 1)
        printf("Stack Overflow\n");
    else {
        top++;
        stack[top] = value;
        printf("Inserted %.2f into stack\n", value);
    }
}

int main() {
    push(5.5);
    push(10.2);
    push(15.8);
    return 0;
}
```

# Output:
<img width="768" height="129" alt="image" src="https://github.com/user-attachments/assets/a553b83b-7e31-4ca3-8d7f-52bf828bd3c2" />

# Result:
Thus, the program to push the given element in to a stack using array is verified successfully


## EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.

# Aim:
To write a C program to display queue elements using array

# Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
# Program:
```
#include <stdio.h>
#define SIZE 5

int queue[SIZE];
int front = -1, rear = -1;

void enqueue(int value) {
    if (rear == SIZE - 1)
        printf("Queue Overflow\n");
    else {
        if (front == -1)
            front = 0;
        queue[++rear] = value;
    }
}

void display() {
    if (front == -1)
        printf("Queue is empty\n");
    else {
        printf("Queue elements are:\n");
        for (int i = front; i <= rear; i++)
            printf("%d ", queue[i]);
        printf("\n");
    }
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);
    display();
    return 0;
}
```
# Output:

<img width="767" height="91" alt="image" src="https://github.com/user-attachments/assets/4326a6b2-a7a6-4fe7-adc4-1bc20ca90f47" />

# Result:
Thus, the program to display queue elements using array is verified successfully.

## EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.

# Aim:
To write a C program to insert elements in queue using array.

# Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

# Program:
```
#include <stdio.h>
#define SIZE 5

float queue[SIZE];
int front = -1, rear = -1;

void enqueue(float value) {
    if (rear == SIZE - 1)
        printf("Queue Overflow\n");
    else {
        if (front == -1)
            front = 0;
        queue[++rear] = value;
        printf("Inserted %.2f into queue\n", value);
    }
}

int main() {
    enqueue(1.5);
    enqueue(2.5);
    enqueue(3.5);
    return 0;
}
```

# Output:

<img width="610" height="111" alt="image" src="https://github.com/user-attachments/assets/dad59c99-ef03-4e10-a92d-7cd72e58d0e1" />

# Result:
Thus, the program to insert elements in queue using array is verified successfully.


## EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY

# Aim:

To create a function in C that deletes an element from a queue implemented using an array.

# Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.

# Program:
```
#include <stdio.h>
#define SIZE 5

int queue[SIZE];
int front = -1, rear = -1;

void enqueue(int value) {
    if (rear == SIZE - 1)
        printf("Queue Overflow\n");
    else {
        if (front == -1)
            front = 0;
        queue[++rear] = value;
    }
}

void dequeue() {
    if (front == -1)
        printf("Queue is empty\n");
    else {
        printf("Deleted element: %d\n", queue[front]);
        front++;
        if (front > rear)
            front = rear = -1;
    }
}

void display() {
    if (front == -1)
        printf("Queue is empty\n");
    else {
        printf("Queue elements are:\n");
        for (int i = front; i <= rear; i++)
            printf("%d ", queue[i]);
        printf("\n");
    }
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);
    display();
    dequeue();
    display();
    return 0;
}
```

# Output:

<img width="581" height="167" alt="image" src="https://github.com/user-attachments/assets/d46d38c9-de83-4e8c-bd5c-dddba89523a7" />

# Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
