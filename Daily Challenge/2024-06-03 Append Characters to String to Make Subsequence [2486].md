# Append Characters to String to Make Subsequence [2486]
You are given two strings s and t consisting of only lowercase English letters.<br><br>
Return the minimum number of characters that need to be appended to the end of s so that t becomes a subsequence of s.<br><br>
A subsequence is a string that can be derived from another string by deleting some or no characters without changing the order of the remaining characters.<br><br>
<hr>

Solution by @krypto-kiddo:<br><br>

```python
class Solution:
    def appendCharacters(self, s: str, t: str) -> int:
        newt = t + "*"
        ptr = 0
        for char in s: 
            if char == newt[ptr]: ptr+=1
        return(len(t)-ptr)
```
<hr>
<h2>Result</h2>
<img src = "https://github.com/krypto-kiddo/leetcode/assets/97212160/2b7d4722-2d25-4de0-8821-4319ea97c811">

