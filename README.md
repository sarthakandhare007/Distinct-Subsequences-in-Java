# Distinct-Subsequences-in-Java
Problem

Given two strings s and t, return the number of distinct subsequences of s which equals t.

A subsequence is formed by deleting some (possibly zero) characters of s without changing the relative order of the remaining characters.


---

Example

Input: s = "rabbbit", t = "rabbit"
Output: 3
Explanation:
There are 3 distinct subsequences:
rabbbit
rabbbit
rabbbit
   ^^ ^^


---

🔹 Intuition

Let’s use Dynamic Programming:

Define

dp[i][j] = number of distinct subsequences of s[0..i-1] that form t[0..j-1].


Recurrence:

If s[i-1] == t[j-1]:

dp[i][j] = dp[i-1][j-1] + dp[i-1][j]

(we can use this character or skip it)

Else:

dp[i][j] = dp[i-1][j]

(only option is to skip it)


Base cases:

dp[i][0] = 1 for all i (empty t always matches)

dp[0][j] = 0 for j > 0 (empty s can't match non-empty t)
