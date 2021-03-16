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
