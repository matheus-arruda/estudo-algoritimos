# 🎯 Problemas Clássicos de DP em Java

## 1. Fibonacci
**Enunciado**:
Calcule o n-ésimo número de Fibonacci.

```java
Input: n = 5
Output: 5 (0, 1, 1, 2, 3, 5)
```

### 🔍 Solução (Bottom-Up)

```java

public int fib(int n) {
    if (n <= 1) return n;
    int[] dp = new int[n + 1];
    dp[0] = 0; dp[1] = 1;
    for (int i = 2; i <= n; i++) {
        dp[i] = dp[i - 1] + dp[i - 2];
    }
    return dp[n];
}
```
-   **Complexidade**: O(n).