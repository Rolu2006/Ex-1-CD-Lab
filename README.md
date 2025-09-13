# Ex-1 IMPLEMENTATION-OF-SYMBOL-TABLE
# Register Number :212224240156
# Date : 13-09-2025
# AIM :
## To write a C program to implement a symbol table.
# ALGORITHM
1.	Start the program.
2.	Get the input from the user with the terminating symbol ‘$’.
3.	Allocate memory for the variable by dynamic memory allocation function.
4.	If the next character of the symbol is an operator then only the memory is allocated.
5.	While reading, the input symbol and memory address are inserted into the symbol table.
6.	The steps are repeated till ‘$’ is reached.
7.	To reach a variable, enter the variable to be searched and the symbol table has been checked for the corresponding variable, the variable along with its address is displayed as a result.
8.	Stop the program. 
# PROGRAM
```
#include <stdio.h>
#include <ctype.h>
#include <string.h>
#include <stdlib.h>

#define MAX_EXPRESSION_SIZE 100

int main() {
	int i = 0, j = 0, x = 0, n, flag = 0;
	int k;
	char b[MAX_EXPRESSION_SIZE], d[15], c, srch;

	printf("Enter the Expression terminated by $: ");
	while ((c = getchar()) != '$' && i < MAX_EXPRESSION_SIZE - 1) {
		b[i++] = c;
	}
	b[i] = '\0';
	n = i - 1;

	printf("\nGiven Expression: %s\n", b);

	printf("\nSymbol Table\n");
	printf("Symbol\tType\t\tAddress\n");

	for (j = 0; j <= n; j++) {
		c = b[j];
		if (isalpha((unsigned char)c)) {
			int alreadyExists = 0;
			for (k = 0; k < x; k++) {
				if (d[k] == c) {
					alreadyExists = 1;
					break;
				}
			}

			if (!alreadyExists) {
				d[x] = c;
				printf("%c\tidentifier\t%p\n", c, (void*)&d[x]);
				x++;
			}
		}
	}

	// Clear input buffer
	while ((c = getchar()) != '\n' && c != EOF);

	printf("\nEnter the symbol to search: ");
	srch = getchar();

	for (i = 0; i < x; i++) {
		if (srch == d[i]) {
			printf("Symbol Found\n");
			flag = 1;
			break;
		}
	}
	if (flag == 0)
		printf("Symbol Not Found\n");

	return 0;
}
```
# OUTPUT
```
Enter the Expression terminated by $: m/n+p*q-r+s$
Given Expression: m/n+p*q-r+s
Symbol Table
Symbol Type Address
m identifier 000000000065FDB1
n identifier 000000000065FDB2
p identifier 000000000065FDB3
q identifier 000000000065FDB4
r identifier 000000000065FDB5
s identifier 000000000065FDB6
Enter the symbol to search: t
Symbol Not Found
--------------------------------
Process exited after 222.6 seconds with return value 0
Press any key to continue . . .
Enter the Expression terminated by $: m/n+p*q-r+s$

Given Expression: m/n+p*q-r+s

Symbol Table
Symbol  Type            Address
m       identifier      000000000065FDB1
n       identifier      000000000065FDB2
p       identifier      000000000065FDB3
q       identifier      000000000065FDB4
r       identifier      000000000065FDB5
s       identifier      000000000065FDB6

Enter the symbol to search: s
Symbol Found

--------------------------------
Process exited after 22.19 seconds with return value 0
Press any key to continue . . .
```
# RESULT
### The program to implement a symbol table is executed and the output is verified.
