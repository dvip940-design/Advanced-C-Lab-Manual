EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.

Aim:

To write a C program to search a given element in the given linked list.

Algorithm:

1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    char data;
    struct Node *next;
};

struct Node *head = NULL;

void insert(char data)
{
    struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;

    if(head == NULL)
    {
        head = newNode;
        return;
    }

    struct Node *temp = head;

    while(temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
}

void search(char key)
{
    struct Node *temp = head;

    while(temp != NULL)
    {
        if(temp->data == key)
        {
            printf("Element Found");
            return;
        }
        temp = temp->next;
    }

    printf("Element Not Found");
}

int main()
{
    insert('A');
    insert('B');
    insert('C');

    search('B');

    return 0;
}
```

Output:

<img width="309" height="64" alt="image" src="https://github.com/user-attachments/assets/6cf5470e-1a39-4e73-8362-1ec4244085af" />




Result:

Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.

Aim:

To write a C program to insert a node in a linked list.

Algorithm:

1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    char data;
    struct Node *next;
};

struct Node *head = NULL;

void insert(char data)
{
    struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));

    newNode->data = data;
    newNode->next = NULL;

    if(head == NULL)
    {
        head = newNode;
        return;
    }

    struct Node *temp = head;

    while(temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
}

void display()
{
    struct Node *temp = head;

    while(temp != NULL)
    {
        printf("%c ", temp->data);
        temp = temp->next;
    }
}

int main()
{
    insert('A');
    insert('B');
    insert('C');

    display();

    return 0;
}
```

Output:

<img width="187" height="52" alt="image" src="https://github.com/user-attachments/assets/ff2fe678-7a40-4ba2-80c0-e16e431b4039" />


 
Result:

Thus, the program to insert a node in a linked list is verified successfully.


 
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST

Aim:

To write a C program to traverse a doubly linked list.

Algorithm:

1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    struct Node *prev;
    int data;
    struct Node *next;
};

struct Node *head = NULL;

void insert(int data)
{
    struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));

    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = NULL;

    if(head == NULL)
    {
        head = newNode;
        return;
    }

    struct Node *temp = head;

    while(temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
    newNode->prev = temp;
}

void traverse()
{
    struct Node *temp = head;

    while(temp != NULL)
    {
        printf("%d ", temp->data);
        temp = temp->next;
    }
}

int main()
{
    insert(10);
    insert(20);
    insert(30);

    traverse();

    return 0;
}
```

Output:

<img width="208" height="57" alt="image" src="https://github.com/user-attachments/assets/daf6903c-905a-4ef7-8037-e04b89ade74a" />



Result:

Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST

Aim:

To write a C program to insert an element in doubly linked list

Algorithm:

1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    struct Node *prev;
    int data;
    struct Node *next;
};

struct Node *head = NULL;

void insert(int data)
{
    struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));

    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = NULL;

    if(head == NULL)
    {
        head = newNode;
        return;
    }

    struct Node *temp = head;

    while(temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
    newNode->prev = temp;
}

void display()
{
    struct Node *temp = head;

    while(temp != NULL)
    {
        printf("%d ", temp->data);
        temp = temp->next;
    }
}

int main()
{
    insert(100);
    insert(200);
    insert(300);

    display();

    return 0;
}
```

Output:

<img width="283" height="61" alt="image" src="https://github.com/user-attachments/assets/563f7ec9-9ed7-4f38-8277-7111d9772ff2" />



Result:

Thus, the program to insert an element in doubly linked list is verified successfully.




EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST




Aim:

To write a C function that deletes a given element from a linked list.

Algorithm:

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


Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *head = NULL;

void insert(int data)
{
    struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));

    newNode->data = data;
    newNode->next = NULL;

    if(head == NULL)
    {
        head = newNode;
        return;
    }

    struct Node *temp = head;

    while(temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
}

void deleteNode(int key)
{
    if(head == NULL)
    {
        printf("List is Empty");
        return;
    }

    struct Node *temp = head;
    struct Node *prev = NULL;

    if(head->data == key)
    {
        head = head->next;
        free(temp);
        return;
    }

    while(temp != NULL && temp->data != key)
    {
        prev = temp;
        temp = temp->next;
    }

    if(temp == NULL)
    {
        printf("Element Not Found");
        return;
    }

    prev->next = temp->next;
    free(temp);
}

void display()
{
    struct Node *temp = head;

    while(temp != NULL)
    {
        printf("%d ", temp->data);
        temp = temp->next;
    }
}

int main()
{
    insert(10);
    insert(20);
    insert(30);

    deleteNode(20);

    display();

    return 0;
}
```

Output:

<img width="189" height="64" alt="image" src="https://github.com/user-attachments/assets/3cc990a5-9342-4d1c-9dd3-4296a62bc8c3" />






Result:

Thus, the function that deletes a given element from a linked list is verified successfully.





