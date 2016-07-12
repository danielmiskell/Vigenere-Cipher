#include <cs50.h>
#include <stdlib.h>
#include <string.h>
#include <stdio.h>
#include <ctype.h>

int main(int argc, string argv[])
{
    if (argc != 2)
    {
        printf("Usage: ./caesar key");
        return 1;
        
    }
    
    string k = argv[1];

    
    for (int j=0; k[j]; j++)
    {
        k[j] = tolower(k[j]);
    }
    
    string p = GetString();
    
    int m = strlen(k);
    int j = 0;
    
    for (int i =0, n=strlen(p); i<n ;i++)
    {
        if (isalpha(p[i])) {
            
                if (isupper(p[i]))
                {
                    int original_letter = p[i];
                    int new_letter = (( original_letter - 97 + k[j%m] - 65) % 26 ) + 65;
            
                    printf("%c", new_letter);
                }
        
                if (islower(p[i]))
                {
                    int original_letter = p[i];
                    int new_letter = (( original_letter - 97 + k[j%m] - 97) % 26 ) + 97;
        
                    printf("%c", new_letter);
            
                }
            
                j++;
        }
        
        else {
            printf("%c", p[i]);
        }
        
        
    }
    return 0;
    
}
