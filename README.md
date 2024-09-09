def coin_change_ways(coins, n, total_sum):
    # Create a dp array to store the number of ways to make each sum
    dp = [0] * (total_sum + 1)
    
    # There's 1 way to make the sum 0, which is to not use any coin
    dp[0] = 1
    
    # Loop through each coin
    for coin in coins:
        # Update the dp array for all sums that can be reached with the current coin
        for j in range(coin, total_sum + 1):
            dp[j] += dp[j - coin]
    
    # Return the number of ways to make the total sum
    return dp[total_sum]

# Example usage:
coins = [1, 2, 3]
n = len(coins)
total_sum = 4

print(coin_change_ways(coins, n, total_sum))  # Output: 4

