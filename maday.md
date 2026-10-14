# Profile: Matthew Adaya

- **NetID:** maday
- **Major:** Computer Science
- **Question that I chose from the memoization exercise:** Climbing Stairs to reach the top
- **Link to the question article:** https://www.geeksforgeeks.org/problems/count-ways-to-reach-the-nth-stair-1587115620/1
- **My solution:**
int countWays(int n) {
    int dp[n + 1];
    
    dp[0] = 1;
    dp[1] = 1;
    
    for(i = 2; i <= n; i++){
        dp[i] = dp[i - 1] + dp[i - 2];
    }
    return dp[n];
    
}
