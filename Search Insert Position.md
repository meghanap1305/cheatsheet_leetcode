# Search Insert Position 
Link : https://leetcode.com/problems/search-insert-position/
## Intuition
Implement binary search through the sorted array and insert the element in the right position if its not found in the array
## Approach 
Sorted arrays choose binary search .It is the most efficient to search for the element

return start
## Complexity 
-Time : O(log n)
-Space : O(1)
## Optimization 
Use only binary search to even identify the right position incase element not found by returning start 
## Code 
``` c
int searchInsert(int* nums, int numsSize, int target) {
    int start=0;
    int end=numsSize-1;
    int idx=-1;
    while(start<=end)
    {
        int mid =(start+(end-start)/2);
        if(nums[mid]==target)
        {
            idx=mid;
            return idx;
        }
        else if(nums[mid]>target)
        {
            end=mid-1;
        }
        else if(nums[mid]<target)
        {
            start=mid+1;
        }
    }
    return start;
}
```
## Takeaways 
Binary search can be used not only to find elements but also to determine insertion positions

When the loop ends, start gives the correct index to insert the target
