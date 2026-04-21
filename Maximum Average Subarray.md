## Maximum Average Subarray
# Link
https://leetcode.com/problems/maximum-average-subarray-i/

# Approach 
Compute the sum of first k elements 

Add the next element and remove the first element basically u have created a sliding window of constant size k

update the glloabl max_sum only when the current sum exceedes the previous sum
# Complexity 
-Time O(n)
-Space O(1)
# Code 
```c
double findMaxAverage(int* nums, int numsSize, int k) {
    double max_sum;
    double sum=0;
    for(int i=0;i<k;i++)
    {
        sum+=nums[i];
    }
    max_sum=sum;
    for(int j=k;j<numsSize;j++)
    {
        sum+=nums[j]-nums[j-k];
    if(sum>max_sum)
      max_sum=sum;
    }
    return max_sum/k;
}
```
# Take away 
Sliding window technique is very useful to reduce the complexity to O(n)
