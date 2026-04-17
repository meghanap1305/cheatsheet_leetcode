## Counting Bits\
# Link : https://leetcode.com/problems/counting-bits/
# Approach 
initialised the base case 
as the number increases 1 or 0 keeps adding to the previous number ,with this observation in mind we check the last number added is 1 or 0 and accordingly add 1
# Complexity 
-Time : O(n)
-Space : O(1)
# Code 
``` c
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* countBits(int n, int* returnSize) {
    int * ptr=(int *) malloc ((n+1)*sizeof(int));
    ptr[0]=0;
    for(int i=1;i<n+1;i++)
    {
        ptr[i]=ptr[i>>1]+(i&1);
    }
    *returnSize=n+1;
    return ptr;
}
```
# Take aways 
4>>1 integer division by 2 ,essentially the right shift operator , allows us to remember the bit count of the previous element 
i&1 isolates the least significant bit (last bit) 
