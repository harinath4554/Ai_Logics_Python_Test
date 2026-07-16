# Ai_Logics_Python_Test


### Problem 1 – Time Slot Consolidation Problem Statement

n = int(input())
arr = []

for i in range(n):
    start, end = map(int, input().split())
    arr.append([start, end])

arr.sort()
start = arr[0][0]
end = arr[0][1]
for j in range(1, n):
    if arr[j][0] <= end:
        if arr[j][1] > end:
            end = arr[j][1]
    else:
        print(start, end)
        start = arr[j][0]
        end = arr[j][1]

print(start, end)



#### Problem 2 – Maximum Signal Strength Problem Statement

n = int(input())
arr = list(map(int, input().split()))
h = int(input())
x = sum(arr[:h])
max = x

for i in range(h, n):
    x = x + arr[i] - arr[i - h]
    if x > max:
        max = x

print(max)





#### Problem 3 – Communication Channel Analyzer Problem Statement

s = input()
dict = {}
l = 0
longest = 0

for i in range(len(s)):
    h = s[i]
    if h in dict and dict[h] >= l:
        l = dict[h] + 1

    dict[h] = i

    length = i - l + 1
    if length > longest:
        longest = length
print(longest)
