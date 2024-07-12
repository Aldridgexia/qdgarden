OA(online assessment) is often the first step in a quant dev/quant research job application. Be it automatically sent or human emailed, you usually need to spare 1 or 2 hours for this timed test. While many tech firms have same setup, OA in quant space has some unique characteristics, which I'll discuss below.

## Big picture: what's the purpose of OA?
In short, OA is purely for shrinking the candidate pool size. Due to the highly competitive market, for any open position, there will be flood of applications in a very short period of time. Even after some hard filtering like year of experience or education background, the number of candidate is still too large for next step. That's when OA comes in handy. With OA, you get to further shrink the candidate pool size. With scores at hand, employer can be flexible enough to select candidates for next step. It just sorts the score and selects top K, with K being a parameter to tune based on many factors.

Realizing the purpose of OA is essential when preparing for it. You don't control the K, so you actually have no guarantee to be selected in that K member group, no matter how well you've done. Therefore, if you fail an OA, it doesn't mean you did a poor job. There is no need to blame youself for not passing an OA, simply because the K might be 1.

## What to prepare for OA?
Many would simply say, algorithms and data structures. Yes, that's correct, but that's also too broad/vague. What specific algorithms and data structures are the favorites? We need a prioritized list.

Based on my personal experience and what I've observed, here are some highly preferred topics for a quant OA.

- array and string
- dfs/bfs
- two dimensional array/matrix
- graph

It may surprise some people that tree is not among the list. That's because tree requires more contexts, and someone without a CS background might not even understand the problem. Employer wants to avoid such scenario that one problem basically asks "have you studied certain type of data structure/algorithm?". Such binary filter can be later applied in phone interviews. For OA, they still want to give everyone an equal opportunity. That's why linked list is also not an ideal option for OA problems.

Array and string questions instead are very intuitive. They can still be extremely difficult to solve, but you get to choose how difficult it needs to be. It requires barely no context so everyone should be able to at least think about some brute force solutions. Usually there can be many solutions, so when it comes to comparing two candidates with same score, employer can still have some leverage on who had a better solution.

Many techniques can also be applied to array and string questions. To name a few, dynamic programming, sliding window, two pointers, greedy. Even graph can be expressed in an array/list. dfs and bfs is too useful to be avoided in an OA question.

## Detail breakdown: short list of topics and example questions
### If you have to pick only one question...

- [Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/)

All time favorite, I've encountered it over and over again in the interview. This is the starting point of a whole series of DP problems with same setup, yet you can write so many solutions, with minimum LOC of 5. So elegant that I have to paste the solution here.
```python
def maxProfit(self, prices: List[int]) -> int:
    min_price, max_profit = prices[0], 0
    for i in range(len(prices)):
        min_price = min(min_price, prices[i])
        max_profit = max(max_profit, prices[i] - min_price)
    return max_profit
```
