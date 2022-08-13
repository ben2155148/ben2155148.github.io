# Welcome!
## Projects
### Roman Numeral to Int Converter
This program converts roman numerals to its integer value representation!
``` cpp 
    int romanToInt(string s) {

           int num = 0;
           
           if(s.length() < 1) {
               cout << "ERROR: TOO SMALL" << endl;
               return -1;
           } else if (s.length() > 15) {
               cout << "ERROR: TOO LARGE" << endl;
               return -1;
           } 
           for(int i = 0; i < s.length(); i++) {
               switch (s[i]) {
                    case 'I': 
                        if((i+1) < s.length() && (s[i+1] == 'V' || s[i+1] == 'X')) {
                            num -= 1;
                        } else {
                            num += 1;
                        }
                        break;
                    case 'V': 
                        num += 5;
                        break;
                    case 'X':  
                        if((i+1) < s.length() && (s[i+1] == 'L' || s[i+1] == 'C')) {
                            num -= 10;
                        } else {
                            num += 10;
                        }
                        break;
                    case 'L': 
                        num += 50;
                        break;
                    case 'C': 
                        if((i+1) < s.length() && (s[i+1] == 'D' || s[i+1] == 'M')) {
                            num -= 100;
                        } else {
                            num += 100;
                        }
                        break;
                    case 'D': 
                        num += 500;
                        break;
                    case 'M': 
                        num += 1000;
                        break;            
               }
           }

           return num;
        }
```
[github repo](https://github.com/ben2155148/RomanNumerals)
___
### Palindrome Number
This program reads an integer and determines whether it is a palindrome!
``` cpp 
    bool isPalindrome(int x) {
            bool palindrome = true;
            
            //convert int to string
            string str = to_string(x);

            //reverse string
            int n = str.length();
            
            for(int i = 0; i < n / 2; i++) {
                swap(str[i], str[n - i - 1]);
            }

            //compare data
            int y = stoi(str);

            if(x != y) 
                palindrome = false;
            
            return palindrome;
        }
```
[github repo](https://github.com/ben2155148/PalindromeNumber)