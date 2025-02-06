<p align="center" width="100%">
    <img src="./asset/utp logo.png" height="100" alt="UTP logo" />
</p>


# TEB2093 Computer Security - Lab 03

## Members

- Ammar Farhan Bin Mohamad Rizam (22006911)
- Amisya Fareezan Binti Mohd Fadhil (22007082)
- Ahmad Anas Bin Azhar (22005996)
- Muhammad Hanis Afifi Bin Azmi (22001602)

### Task 1
#### Monoalphabetic substitution cipher
### Code:
```html
#include<iostream>
#include<string.h>
using namespace std;
int main() {
   cout<<"Enter the message:\n";
   char msg[100];
   cin.getline(msg,100); //take the message as input
   int i, j, length,choice,key;
   cout << "Enter key(0-25): ";
   cin >> key; //take the key as input
   length = strlen(msg);
   cout<<"Enter your choice \n1. Encryption \n2. Decryption \n";
   cin>>choice;
   if (choice==1) //for encryption
   {
      char ch;
      for(int i = 0; msg[i] != '\0'; ++i) {
         ch = msg[i];
         //encrypt for lowercase letter
         if (ch >= 'a' && ch <= 'z'){
            ch = ch + key;
            if (ch > 'z') {
               ch = ch - 'z' + 'a' - 1;
            }  
            msg[i] = ch;
         }
         //encrypt for uppercase letter
         else if (ch >= 'A' && ch <= 'Z'){
            ch = ch + key;
            if (ch > 'Z'){
               ch = ch - 'Z' + 'A' - 1;
            }
            msg[i] = ch;
         }
      }
      printf("Encrypted message: %s", msg);
   }
   else if (choice == 2) { //for decryption
      char ch;
      for(int i = 0; msg[i] != '\0'; ++i) {
         ch = msg[i];
         //decrypt for lowercase letter
         if(ch >= 'a' && ch <= 'z') {
            ch = ch - key;
            if(ch < 'a'){
               ch = ch + 'z' - 'a' + 1;
            }
            msg[i] = ch;
         }
         //decrypt for uppercase letter
         else if(ch >= 'A' && ch <= 'Z') {
            ch = ch - key;
            if(ch < 'A') {
               ch = ch + 'Z' - 'A' + 1;
            }
            msg[i] = ch;
         }
      }
      cout << "Decrypted message: " << msg;
   }
}
```
### Encryption:
(./asset/encrypt_mono.png)
### Decryption:

