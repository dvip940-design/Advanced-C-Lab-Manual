EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:

To write a C program to display stack elements using an array.

Algorithm:

1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:

```c
#include <stdio.h>

#define SIZE 5

int stack[SIZE];
int top = -1;

void display()
{
    if(top == -1)
    {
        printf("Stack is Empty");
        return;
    }

    printf("Stack Elements:\n");

    for(int i = top; i >= 0; i--)
    {
        printf("%d ", stack[i]);
    }
}

int main()
{
    stack[++top] = 10;
    stack[++top] = 20;
    stack[++top] = 30;

    display();

    return 0;
}
```

Output:

<img width="376" height="96" alt="image" src="https://github.com/user-attachments/assets/53632615-7f06-406c-833a-baa67ef27070" />




Result:

Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.

Aim:

To create a C program to push the given element in to a stack using array.

Algorithm:

1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:

```c
#include <stdio.h>

#define SIZE 5

float stack[SIZE];
int top = -1;

void push(float data)
{
    if(top == SIZE - 1)
    {
        printf("Stack Overflow");
        return;
    }

    stack[++top] = data;
}

int main()
{
    push(10.5);
    push(20.5);
    push(30.5);

    printf("Elements in Stack:\n");

    for(int i = top; i >= 0; i--)
    {
        printf("%.1f ", stack[i]);
    }

    return 0;
}
```

Output:

<img width="409" height="84" alt="image" src="https://github.com/user-attachments/assets/fe3db448-9103-430a-94ac-5970457d18e4" />





Result:

Thus, the program to push the given element in to a stack using array is verified successfully


 
EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.

Aim:

To write a C program to display queue elements using array

Algorithm:

1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:

```c
#include <stdio.h>

#define SIZE 5

int queue[SIZE];
int front = 0;
int rear = 2;

void display()
{
    if(front > rear)
    {
        printf("Queue is Empty");
        return;
    }

    printf("Queue Elements:\n");

    for(int i = front; i <= rear; i++)
    {
        printf("%d ", queue[i]);
    }
}

int main()
{
    queue[0] = 10;
    queue[1] = 20;
    queue[2] = 30;

    display();

    return 0;
}
```

Output:

<img width="437" height="96" alt="image" src="https://github.com/user-attachments/assets/b8062a3a-b9b1-4608-b759-9bfd911a8ee6" />


Result:

Thus, the program to display queue elements using array is verified successfully.


 
EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.

Aim:

To write a C program to insert elements in queue using array.

Algorithm:

1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:

```c
#include <stdio.h>

#define SIZE 5

float queue[SIZE];
int front = -1;
int rear = -1;

void enqueue(float data)
{
    if(rear == SIZE - 1)
    {
        printf("Queue Overflow");
        return;
    }

    if(front == -1)
        front = 0;

    queue[++rear] = data;
}

int main()
{
    enqueue(10.5);
    enqueue(20.5);
    enqueue(30.5);

    printf("Queue Elements:\n");

    for(int i = front; i <= rear; i++)
    {
        printf("%.1f ", queue[i]);
    }

    return 0;
}
```

Output:

<img width="395" height="82" alt="image" src="https://github.com/user-attachments/assets/7b876984-c301-427a-b304-639d4e0eb85c" />


Result:

Thus, the program to insert elements in queue using array is verified successfully.



 
EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:

```c
#include <stdio.h>

#define SIZE 5

int queue[SIZE];
int front = 0;
int rear = 2;

void dequeue()
{
    if(front == -1 || front > rear)
    {
        printf("Queue is Empty");
        return;
    }

    printf("Deleted Element = %d\n", queue[front]);
    front++;

    if(front > rear)
    {
        front = -1;
        rear = -1;
    }
}

int main()
{
    queue[0] = 10;
    queue[1] = 20;
    queue[2] = 30;

    dequeue();

    printf("Queue after Deletion:\n");

    for(int i = front; i <= rear; i++)
    {
        printf("%d ", queue[i]);
    }

    return 0;
}
```

Output:

<img width="437" height="131" alt="image" src="https://github.com/user-attachments/assets/193ebed6-140f-4c84-bfc8-8ca710d17c62" />



Result:

Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
