## Sqrt(x)
# link :https://leetcode.com/problems/sqrtx/
# Approach 
using binary search approach find the correct element whose square matches the target  
# code 
``` c
int mySqrt(int x) {
    if(x==0 || x==1)
      return x;
    int s=1;
    int e=x;
    int ans=0;
    while(s<=e)
    {
        int m=s+((e-s)/2);
        long square=(long) m*m;
        if(square==x)
        {
        ans=m;
          return m;
        }
        else if(square>x)
        {
            e=m-1;
        }
        else
        {
            ans=m;
            s=m+1; 
        }
    }
    return ans;
}
```
# Takeaways 
If square > x: The number m is too large. We don't update ans and look in the lower half.

If square < x: The number m could be the answer, or the answer could be even larger. We store m in ans just in case, then look in the upper half to see if there’s a better (larger) fit.
