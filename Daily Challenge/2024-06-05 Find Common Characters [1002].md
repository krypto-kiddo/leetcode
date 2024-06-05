# Find Common Characters [1002]

Given a string array words, return an array of all characters that show up in all strings within the words (including duplicates). <br><br>
You may return the answer in any order.<br><br>
<b>Example:</b><br>
&emsp;Input: words = ["bella","label","roller"]<br>
&emsp;Output: ["e","l","l"]
<hr>

Solution by @krypto-kiddo:<br><br>

```python
# Solved this in under 23 Minutes, but no one would belive me so anyway
class Solution:
    def commonChars(self, words: List[str]) -> List[str]:

        def StringToAsc(string):
            alpha = [0]*26
            for char in string: 
                alpha[ord(char)-97]+=1  # String to ASCII relative list
            return(alpha)

        def AscToString(alphaset):
            str2 = ""
            for i in range(26):
                str2 += chr(i+97)*alphaset[i] # ASCII relative list to String
            return(str2)
        
        def MinAsc(alphaset1,alphaset2):
            minAlpha = [0]*26
            for i in range(26):
                minAlpha[i] = min(alphaset1[i],alphaset2[i])
            return(minAlpha)

        
        alp1 = StringToAsc(words[0])

        for i in range(1,len(words)):
            alp2 = StringToAsc(words[i])
            alp1 = MinAsc(alp1,alp2)
        
        return(AscToString(alp1))
```
<hr>
<h2>Result</h2>
<img src = "https://github.com/krypto-kiddo/leetcode/assets/97212160/99b13bd9-58dc-477b-bfbe-744bab3a7bf0">
