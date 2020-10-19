---
layout: post
title: CandyCrush1D
gh-badge: [star, fork, follow]
tags: [Array,Stack]
comments: true
---
[refer](https://leetcode.com/discuss/interview-question/380650/Bloomberg-or-Phone-Screen-or-Candy-Crush-1D/342375)
```python
"""
main idea: loop through each char and count char that is same in the row, until encounter a different char, store previous char and cnt into stack; then check if candies can be crushed by checking top of stack, if yes, crush candies first before push new char and cnt  into stack;
note  the new char can be the same as char stored at top stack after crushing operation, so before push new char into stack, check if new char is same; if yes, just update directly from top stack, if not, push the new char and cnt (set as 1) into stack;
in the end, check if items remains in stack have candies to be crushed, if yes, perform crush.  

"""
# time O(N) space O(N)
def candy_crush(candies):
    if not candies:
        return candies
    
    stack = []
    stack.append([candies[0], 1])
    
    for i in range(1, len(candies)):
        if candies[i] != candies[i-1]:
            if stack[-1][1] >= 3:
                stack.pop()
            if stack and stack[-1][0] == candies[i]:
                stack[-1][1] += 1
            else:
                stack.append([candies[i], 1])
        else:
            stack[-1][1] += 1
            
    # handle end
    if stack[-1][1] >= 3:
        stack.pop()
        
    out = []
    for char_freq in stack:
        out += char_freq[0] * char_freq[1]
        #print(out,'out')
    
    return ''.join(out)
    
print(candy_crush("aaaabbbc")) #c
print(candy_crush("aabbbacd")) #cd
print(candy_crush("aabbccddeeedcba")) #blank expected
print(candy_crush("aabbbaacd")) #cd
print(candy_crush("dddabbbbaccccaax")) #x
```