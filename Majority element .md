## Majorrity Element 
# Link 
https://leetcode.com/problems/majority-element/
# Approach 
Set the first element as the candidate and initialize count to 1.

Traverse the array starting from the second element.If count drops to 0, pick the current element as the new candidate and reset count to 1.If the current element matches the candidate, increment count.Otherwise, decrement count.

The remaining candidate at the end of the pass is the majority element.

The algorithm works on a cancellation principle. Since the majority element appears more than n\2 times it will always outlast all other elements combined.
# Complexity 
-Time : O(n)
-Space : O(1)

# Code
```c
int majorityElement(int* nums, int numsSize) {
    int candidate=nums[0];
    int count=1;
    for(int i=1;i<numsSize;i++)
    {
        
        if(count==0)
        {
            candidate=nums[i];
            count =1;
        }
        else if(nums[i]==candidate)
        {
            count++;
        }
        else{
            count--;
        }
    }
    return candidate;
}
```
# Take away 
This is Boyer-Moore voting algorithm , widely used to find the element with highest frequency of occurence.It reduces the space complexity O(1) without any hash maps .This works only if the majority element presence in the array is guaranteed to be more than n/2  
