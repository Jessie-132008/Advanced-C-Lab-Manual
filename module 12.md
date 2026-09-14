

EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display stack elements using linked list.

Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
Program:

```


#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node *head = NULL;

void display() {
    struct Node *p = head;

    printf("Stack elements are:\n");

    while (p != NULL) {
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main() {
    struct Node *p1, *p2, *p3;

    p1 = (struct Node *)malloc(sizeof(struct Node));
    p2 = (struct Node *)malloc(sizeof(struct Node));
    p3 = (struct Node *)malloc(sizeof(struct Node));

    p1->data = 30;
    p1->next = p2;

    p2->data = 20;
    p2->next = p3;

    p3->data = 10;
    p3->next = NULL;

    head = p1;

    display();

    return 0;
}

```

Output:

<img width="532" height="427" alt="image" src="https://github.com/user-attachments/assets/1bbcb5aa-511d-4b4b-820d-9e20cfd71039" />



Result:
Thus, the program to display stack elements using linked list is verified successfully. 



EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
Aim:
To write a C program to pop an element from the given stack using liked list.

Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
Program:

```


#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node *head = NULL;

void display() {
    struct Node *p = head;

    printf("Stack elements are:\n");

    while (p != NULL) {
        printf("%d\n", p->data);
        p = p->next;
    }
}

void pop() {
    struct Node *p;

    if (head == NULL) {
        printf("Stack is empty.\n");
    } else {
        p = head;
        printf("Popped element: %d\n", head->data);
        head = head->next;
        free(p);
    }
}

int main() {
    struct Node *p1, *p2, *p3;

    p1 = (struct Node *)malloc(sizeof(struct Node));
    p2 = (struct Node *)malloc(sizeof(struct Node));
    p3 = (struct Node *)malloc(sizeof(struct Node));

    p1->data = 30;
    p1->next = p2;

    p2->data = 20;
    p2->next = p3;

    p3->data = 10;
    p3->next = NULL;

    head = p1;

    printf("Before POP:\n");
    display();

    pop();

    printf("\nAfter POP:\n");
    display();

    return 0;
}

```

Output:

<img width="528" height="487" alt="image" src="https://github.com/user-attachments/assets/cbcf68c2-78c0-4d9b-a3d9-7bbb140a99ee" />




Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display queue elements using linked list.
Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
Program:

```

#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void enqueue(int value) {
    struct Node *p;

    p = (struct Node *)malloc(sizeof(struct Node));

    p->data = value;
    p->next = NULL;

    if (front == NULL) {
        front = p;
        rear = p;
    } else {
        rear->next = p;
        rear = p;
    }
}

void display() {
    struct Node *p = front;

    printf("Queue elements are:\n");

    while (p != NULL) {
        printf("%d\n", p->data);
        p = p->next;
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

Output:

<img width="532" height="373" alt="image" src="https://github.com/user-attachments/assets/320048aa-51ba-47aa-95f3-efa02c6b69ff" />


Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim:
To write a C program to insert elements in queue using linked list

Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
Program:

```

#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void enqueue(int value) {
    struct Node *p;

    p = (struct Node *)malloc(sizeof(struct Node));

    p->data = value;
    p->next = NULL;

    if (front == NULL) {
        front = p;
        rear = p;
    } else {
        rear->next = p;
        rear = p;
    }

    printf("%d inserted into queue\n", value);
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);

    return 0;
}


```

Output:

<img width="588" height="488" alt="image" src="https://github.com/user-attachments/assets/42e08ff7-93a7-4f5d-a44c-22750e034b7c" />


Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

Program:

```



#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void enqueue(int value) {
    struct Node *p;

    p = (struct Node *)malloc(sizeof(struct Node));

    p->data = value;
    p->next = NULL;

    if (front == NULL) {
        front = p;
        rear = p;
    } else {
        rear->next = p;
        rear = p;
    }
}

void peek() {
    if (front == NULL) {
        printf("Queue is empty.\n");
    } else {
        printf("Peek element: %d\n", front->data);
    }
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);

    peek();

    return 0;
}


```

Output:

<img width="572" height="247" alt="image" src="https://github.com/user-attachments/assets/8249838e-a8e5-4376-9fa0-cc6a52155b31" />




Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


