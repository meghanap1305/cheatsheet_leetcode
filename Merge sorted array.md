## Merge sorted array
# Link : https://leetcode.com/problems/merge-sorted-array/
# Approach 
create three pointer , two pointing to the end of the first and second array and the third to fill the array in the correct order
# Complexity 
- Time O(m+n)
- space O(1)
# code
``` c
void merge(int* nums1, int nums1Size, int m, int* nums2, int nums2Size, int n) {
int p1=m-1;
int p2=n-1;
int p3=m+n-1;
while(p1>=0 && p2>=0) 
{
    if(nums1[p1]>=nums2[p2])
    {
        nums1[p3]=nums1[p1];
        p1--;
    }
    else
    {
        nums1[p3]=nums2[p2];
        p2--;
    }
    p3--;
}   
while(p2>=0)
{
    nums1[p3]=nums2[p2];
    p2--;
    p3--;
}
}
```
# Take aways
Two / three pointer approach is highly effective for linear sorted data structures 

Reverse Traversal: Crucial when working with in-place array modifications.
