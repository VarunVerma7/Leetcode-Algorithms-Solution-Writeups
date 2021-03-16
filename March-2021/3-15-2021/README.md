# https://leetcode.com/problems/custom-sort-string/submissions/

Got answer correct

class Solution:
def customSortString(self, S: str, T: str) -> str:
t = ""
excess = []
for x in S:
while x in T:
index = T.index(x)
t += x
T = T[:index] + T[index + 1:]

    # What letters of T still remain


        return t + T

Basically just loop through S and get all the characters of T in that in S, and then get all the remaining characters afterwards

Here's the top rated solution: Lets dissect how this work

    def customSortString(self, S: str, T: str) -> str:
        ans, cnt = [], collections.Counter(T)           # count each char in T.
        for c in S:
            if cnt[c]: ans.extend(c * cnt.pop(c))       # sort chars both in T and S by the order of S.
        for c, v in cnt.items():
            ans.extend(c * v)                           # group chars in T but not in S.
        return ''.join(ans);

So answer is empty, cnt is the occurence of each character in T, get that many characters in T, then get all the remaining characters
