# code-alph
#include<iostream>
using namespace std;

void Encryption(string term, int key){
    string encrypted = "";
    for (int i = 0; i < term.length(); i++) {
        char c = term[i];
        if (c >= 'a' && c <= 'z') {
            encrypted += 'a' + (c - 'a' + key) % 26; // Handle lowercase
        } else if (c >= 'A' && c <= 'Z') {
            encrypted += 'A' + (c - 'A' + key) % 26; // Handle uppercase
        } else {
            encrypted += c; // Non-alphabet characters remain unchanged
        }
    }
    cout << "Encrypted: " << encrypted << endl;
}

void Decryption(string terms, int keys) {
    string decrypted = "";
    for (int i = 0; i < terms.length(); i++) {
        char c = terms[i];
        if (c >= 'a' && c <= 'z') {
            decrypted += 'a' + (c - 'a' - keys + 26) % 26; // Handle lowercase
        } else if (c >= 'A' && c <= 'Z') {
            decrypted += 'A' + (c - 'A' - keys + 26) % 26; // Handle uppercase
        } else {
            decrypted += c; // Non-alphabet characters remain unchanged
        }
    }
    cout << "Decrypted: " << decrypted << endl;
}
int main(){
    string term,terms;
    int key,keys,choice;
    do{
        cout<<"1. Encryption"<<endl;
        cout<<"2. Decryption"<<endl;
        cout<<"3. Exit"<<endl;
        cout<<"Enter your choice: ";
        cin>>choice;
        switch(choice){
                case 1:
                cout<<"Enter the term: ";
                cin>>term;
                cout<<"Enter the key: ";
                cin>>key; 
                Encryption(term,key);
                break;
            case 2:
                cout<<"Enter the term: ";
                cin>>terms;
                cout<<"Enter the key: ";
                cin>>keys;
                Decryption(terms,keys);
                break;
            case 3:
                return 0;    
            default:
                cout<<" Invalid choice try again "<<endl;
                break;
        }
    }while(true);

}
