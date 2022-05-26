# 25-5-2022-ASS-1
Assignment-1
class Solution:
    def minCostClimbingStairs(self, cost: List[int]) -> int:
        n = len(cost)
        dp = [0] * 3  
        for i in range(2, n + 1):
            jumpOneStep = dp[(i-1) % 3] + cost[i-1]   
            jumpTwoStep = dp[(i-2) % 3] + cost[i-2]  
            dp[i % 3] = min(jumpOneStep, jumpTwoStep)
        return dp[n % 3]
