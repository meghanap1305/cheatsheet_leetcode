# Two Sum
Link : https://leetcode.com/problems/two-sum/
## Intuition
Check every pair of elements in the array and see if their sum equals the target.
## Approach
iterate through the array using a loop
for each element ,calculate the required value 
needed=target-nums[i]
check for search in the array and return the indices
## Complexity
-Time : O(n^2)
-Space :O(1)
## code
``` c
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* twoSum(int* nums, int numsSize, int target, int* returnSize) {
   int *result =(int*)malloc(2 *sizeof(int)) ;
   for(int i=0;i<numsSize;i++)
   {
    int ans=target-nums[i]; 
    for(int j=i+1;j<numsSize;j++)
    {
        if(nums[j]==ans)
        {
            result [0]=i;
            result[1]=j;
            *returnSize=2;
            return result;
        }
    }
   }
   *returnSize=2;
   return result;
}
```
## Optimizations 
Instead of checking all previous elements repeatedly, we can store them and look up the required value instantly using hashing, reducing the time complexity from O(n²) to O(n).
