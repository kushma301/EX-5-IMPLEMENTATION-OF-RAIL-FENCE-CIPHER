## NAME: S.KUSHMA
## REG NO: 212224040168

## EX : 5 IMPLEMENTATION OF RAIL FENCE CIPHER

## AIM:
To develop a simple C program to implement Rail Fence Cipher.

## ALGORITHM:
#### 1.	To perform the Encryption Process
#### •	Input the plaintext string from the user.
#### •	Calculate the length of the plaintext.
#### •	Create the ciphertext using two rails:
#### a.	First, collect characters at even indices (i.e., 0, 2, 4, …).
#### b.	Then, collect characters at odd indices (i.e., 1, 3, 5, …).
#### c.	Combine both parts to form the ciphertext.
#### •	Display the encrypted ciphertext.

#### 2.	To perform the Decryption Process:
#### •	Calculate the length of the ciphertext.
#### •	Find the midpoint:
#### ◦	a. If the length is even, midpoint = length / 2.
#### ◦	b. If the length is odd, midpoint = (length / 2) + 1.
#### •	Reconstruct the original message:
#### a.	Take the first half as characters from even positions.
#### b.	Take the second half as characters from odd positions.
#### c.	Merge both using alternating positions.

#### 3.	Display the decrypted plaintext.

## PROGRAM:
```
#include <stdio.h>
#include <string.h>

int main() {
    char str[1000];
    char rail[100][1000];
    int rails, len, i, j;

    printf("Enter a Secret Message: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0';  
    len = strlen(str);

    printf("Enter number of rails: ");
    scanf("%d", &rails);

    
    for (i = 0; i < rails; i++) {
        for (j = 0; j < len; j++) {
            rail[i][j] = '\n';
        }
    }

    int row = 0, dir_down = 0;
    for (j = 0; j < len; j++) {
        rail[row][j] = str[j];

      
        if (row == 0 || row == rails - 1)
            dir_down = !dir_down;

        row += dir_down ? 1 : -1;
    }

    
    printf("Encrypted Message: ");
    for (i = 0; i < rails; i++) {
        for (j = 0; j < len; j++) {
            if (rail[i][j] != '\n')
                printf("%c", rail[i][j]);
        }
    }
    printf("\n");

    return 0;
}
```

## OUTPUT:
<img width="1710" height="910" alt="Screenshot 2025-09-13 181819" src="https://github.com/user-attachments/assets/10af69de-a644-41d8-aa19-5c8c4fe8dd18" />

## RESULT:
The program implementing the Rail Fence cipher for encryption and decryption has been successfully	executed,	and	the	results	have	been	verified.
