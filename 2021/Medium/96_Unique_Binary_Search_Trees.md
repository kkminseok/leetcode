**python**

```python
class Solution:
    def numTrees(self, n: int) -> int:
        dp =[0] * 20
        dp[0] = 1
        dp[1] = 1
        for i in range(2,n+1):
            for j in range(1,i+1):
                dp[i] = dp[i] + dp[j-1] * dp[i-j]
        return dp[n]
```

-----  

**c++**

```c++
class Solution {
public:
    int numTrees(int n) {
        int dp[20]={0,};
        dp[0] = 1;
        dp[1] = 1;
        for(int i = 2; i <= n ;++i)
            for(int j = 1;j<=i;++j)
                dp[i] += (dp[j-1] * dp[i-j]);
        return dp[n];
    }
};
```