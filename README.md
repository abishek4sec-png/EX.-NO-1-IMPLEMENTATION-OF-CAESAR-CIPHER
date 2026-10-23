# EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER

## AIM:
To implement the simple substitution technique named Caesar cipher using C language.

## ALOGORITHM:

STEP-1: Read the plain text from the user.

STEP-2: Read the key value from the user.

STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.

STEP-4: Else subtract the key from the plain text.

STEP-5: Display the cipher text obtained above.

## PROGRAM:
```

#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main()
{
    char plain[1000], cipher[1000];
    int key, i, length;

    printf("\nEnter the plain text: ");
    fgets(plain, sizeof(plain), stdin);

    // Remove newline character
    plain[strcspn(plain, "\n")] = '\0';

    printf("\nEnter the key value: ");
    scanf("%d", &key);

    // Convert key into range 0-25
    key = key % 26;

    length = strlen(plain);

    printf("\nPLAIN TEXT: %s", plain);

    printf("\n\nENCRYPTED TEXT: ");

    for (i = 0; i < length; i++)
    {
        cipher[i] = plain[i];

        if (isupper(plain[i]))
        {
            cipher[i] = (plain[i] - 'A' + key) % 26 + 'A';
        }
        else if (islower(plain[i]))
        {
            cipher[i] = (plain[i] - 'a' + key) % 26 + 'a';
        }

        printf("%c", cipher[i]);
    }

    cipher[length] = '\0';

    printf("\n\nAFTER DECRYPTION: ");

    for (i = 0; i < length; i++)
    {
        plain[i] = cipher[i];

        if (isupper(cipher[i]))
        {
            plain[i] = (cipher[i] - 'A' - key + 26) % 26 + 'A';
        }
        else if (islower(cipher[i]))
        {
            plain[i] = (cipher[i] - 'a' - key + 26) % 26 + 'a';
        }

        printf("%c", plain[i]);
    }

    plain[length] = '\0';

    return 0;
}

```

## OUTPUT:
<img width="935" height="276" alt="image" src="https://github.com/user-attachments/assets/de57d7de-4b87-4dcd-b2a2-f0ff775f7172" />



## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully.
