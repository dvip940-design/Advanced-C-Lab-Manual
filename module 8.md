EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER

Aim:

To write a C program print the lowercase English word corresponding to the number

Algorithm:

1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:

```c
#include <stdio.h>

int main()
{
    int n;
    scanf("%d", &n);

    switch(n)
    {
        case 1: printf("one"); break;
        case 2: printf("two"); break;
        case 3: printf("three"); break;
        case 4: printf("four"); break;
        case 5: printf("five"); break;
        case 6: printf("six"); break;
        case 7: printf("seven"); break;
        case 8: printf("eight"); break;
        case 9: printf("nine"); break;
        default: printf("Greater than 9");
    }

    return 0;
}
```




Output:


<img width="484" height="211" alt="image" src="https://github.com/user-attachments/assets/5bb1f98c-b747-44dc-89dc-b294d5b5cbf0" />







Result:

Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .

Aim:

To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.

Algorithm:

1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:

```c
#include <stdio.h>

int main()
{
    char a[50];
    int count[10] = {0};

    scanf("%s", a);

    for(int i = 0; a[i] != '\0'; i++)
    {
        if(a[i] >= '0' && a[i] <= '9')
            count[a[i] - '0']++;
    }

    for(int i = 0; i < 10; i++)
        printf("%d ", count[i]);

    return 0;
}
```




Output:


<img width="465" height="203" alt="image" src="https://github.com/user-attachments/assets/1c9e7a59-a612-4197-b0f8-0a6007e71b0f" />







Result:

Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.

Aim:

To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:

1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:

```c
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

int compare(const void *a, const void *b)
{
    return (*(char *)a - *(char *)b);
}

void swap(char *a, char *b)
{
    char t = *a;
    *a = *b;
    *b = t;
}

void reverse(char *s, int start, int end)
{
    while(start < end)
    {
        swap(&s[start], &s[end]);
        start++;
        end--;
    }
}

int nextPermutation(char *s, int n)
{
    int i = n - 2;

    while(i >= 0 && s[i] >= s[i + 1])
        i--;

    if(i < 0)
        return 0;

    int j = n - 1;

    while(s[j] <= s[i])
        j--;

    swap(&s[i], &s[j]);
    reverse(s, i + 1, n - 1);

    return 1;
}

int main()
{
    char s[100];

    scanf("%s", s);

    int n = strlen(s);

    qsort(s, n, sizeof(char), compare);

    do
    {
        printf("%s\n", s);
    }
    while(nextPermutation(s, n));

    return 0;
}
```




Output:


<img width="458" height="390" alt="image" src="https://github.com/user-attachments/assets/37cca78a-c6e7-4706-9308-dee0b9a47061" />







Result:

Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
Aim:

To write a C program to print a pattern of numbers from 1 to n as shown below.

Algorithm:

1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:

```c
#include <stdio.h>

int main()
{
    int n;
    scanf("%d", &n);

    int len = 2 * n - 1;

    for(int i = 0; i < len; i++)
    {
        for(int j = 0; j < len; j++)
        {
            int top = i;
            int left = j;
            int right = len - 1 - j;
            int bottom = len - 1 - i;

            int min = top;

            if(left < min) min = left;
            if(right < min) min = right;
            if(bottom < min) min = bottom;

            printf("%d ", n - min);
        }
        printf("\n");
    }

    return 0;
}
```



Output:


<img width="558" height="439" alt="image" src="https://github.com/user-attachments/assets/23734469-7f5a-419e-84e4-69717ff8a2fd" />







Result:

Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

Program:

```c
#include <stdio.h>

int square()
{
    int n;
    scanf("%d", &n);

    return n * n;
}

int main()
{
    int result;

    result = square();

    printf("Square = %d", result);

    return 0;
}
```




Output:


<img width="323" height="206" alt="image" src="https://github.com/user-attachments/assets/821608b2-235d-4259-9399-56193c58b7cd" />






Result:

Thus, the program is verified successfully



























