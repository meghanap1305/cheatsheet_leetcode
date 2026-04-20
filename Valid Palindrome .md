Valid Palindrome 
# Link
https://leetcode.com/problems/valid-palindrome/
# Approach 
Using two pointer technique to iterate throught the array from left and right 

If the left character is not alphanumeric,else if the right character is not alphanumeric skip the element 

Else if the two characters are not the same return false
# Complexity 
-Time : 0(n) 

-Space :O(1)
# Code 
```c
bool isPalindrome(char* s) {
    int left=0;
    int right=strlen(s)-1;
    while(left<right)
    {
        if(! isalnum(*(s+left)))
          left++;
        else if(! isalnum(*(s+right)))
          right--;
        else {
        if(tolower(*(s+left)) != tolower(*(s+right)))
        {
            return false;
        }
        left++;
        right--;
        }
    }
    return true;
}
```
# Take away :
Good application of Two pointer technique preventing string modification .

The algorithm for palindrome sequence 
