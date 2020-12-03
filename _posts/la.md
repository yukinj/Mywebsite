---
layout: post
title: 1100. Find K-Length Substrings With No Repeated Characters
gh-badge: [star, fork, follow]
tags: [String,Sliding Window]
comments: true
---
main idea: use HashMap to record occurance of unique char within current window, while keep sliding window size as K. condition to determin no repeated character: hmap size == K 
```python
class Solution:
# time O(N)  space O(K)
    def numKLenSubstrNoRepeats(self, S: str, K: int) -> int:
        n =  len(S)
        d = {}
        cnt = 0
        if n< K:
            return cnt
        l=r=0
        while r < n:
            d[S[r]]= d.get(S[r],0)+1
            if r >= K-1:
                if len(d) == K:
                    cnt += 1 
                if d[S[l]] == 1:
                     d.pop(S[l])
                else:
                     d[S[l]] -= 1 
                l += 1 
            r += 1 
        return cnt 
```