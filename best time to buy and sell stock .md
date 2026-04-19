## Best Time To Buy And Sell Stock
#Link : 
https://leetcode.com/problems/best-time-to-buy-and-sell-stock/
# Intuition :
Find the min element in the array ,it should not be the last element cause u can not sell it ,imagine the min element is found in the ith position and now find for max element from i to n-1 using else if
# Approach :
Initialize min to the first price and max_profit to 0.

Iterate through the prices .

If the current price is lower than our min, update min.

Otherwise, calculate the difference between the current price and min. If this difference is greater than max_profit, update max_profit.

This ensures we always sell after we buy.
# Complexity :
-Time :O(n)
-Space: O(1)
# Code :
```c
int maxProfit(int* prices, int pricesSize) {
    int min_price=prices[0];
    int max_profit=0;
    for(int i=0;i<pricesSize;i++)
    {
        if(prices[i]<min_price){
        min_price=prices[i];
        }
        else if(prices[i]-min_price>max_price){
            max_price=prices[i]-min_price;
        }
    }
        return max_price;
}
```

# Take away :
The algorithm is very important and interesting cause it reduces complexity from nested loop to linear scan .Instead of comparing every possible pair of days, we only track the global minimum price seen so far. This allows us to calculate the maximum potential profit at each step in a single pass.
