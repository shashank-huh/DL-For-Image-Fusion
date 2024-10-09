# Welcome, L1 Heading
## L2 Heading
### L3 Heading

**Text in Bold**

*Text in Italic*

## Colors
* Red
* Blue
* Green

`mkdir`

```c++
#include <iostream>
#include <string>
#include <algorithm>
#include <cctype>

using namespace std;

bool isPalindrome(const string& str) { 
    string cleaned;
    for (char c : str) {
        if (isalnum(c)) {
            cleaned += tolower(c);
        }
    }
    string reversed = cleaned;
    reverse(reversed.begin(), reversed.end());
    return cleaned == reversed;
}

int main() {
    string input;
    cout << "Enter a string: "; 
    getline(cin, input);
    string reversed = input;
    reverse(reversed.begin(), reversed.end());
    
    int vowels = 0, consonants = 0, digits = 0, spaces = 0, specialChars = 0;
    
    for (char c : input) {
        if (isalpha(c)) {
            char lower = tolower(c);
            if (lower == 'a' || lower == 'e' || lower == 'i' || lower == 'o' || lower == 'u') {
                vowels++;
            } else {
                consonants++;
            }
        } else if (isdigit(c)) {
            digits++;
        } else if (isspace(c)) {
            spaces++;
        } else {
            specialChars++;
        }
    }
    
    cout << "Number of characters: " << input.length() << endl;
    cout << "The reversed string is: " << reversed << endl;
    cout << "Is it a palindrome? " << (isPalindrome(input) ? "Yes" : "No") << endl;
    cout << "Number of vowels: " << vowels << endl;
    cout << "Number of consonants: " << consonants << endl;
    cout << "Number of digits: " << digits << endl;
    cout << "Number of spaces: " << spaces << endl;
    cout << "Number of special characters: " << specialChars << endl;
    
    return 0;
}

