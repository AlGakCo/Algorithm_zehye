## 단어수학 

[1339](https://www.acmicpc.net/problem/1339)

- 민식이는 수학학원에서 숙제를 받았다.
- 0-9까지의 수를 알파벳 하나로 나타낸 것이다. 문자가 2개 주어졌을 때, 그 두 수의 합을 최대로 만드는 것
- 예를 들어, MCR + ACDEB를 계산한다고 할 때,
- A = 9, B = 4, C = 8, D = 6, E = 5, R = 3, M = 7로 결정한다면, 두 수의 합은 99437이 되어서 최대가 될 것이다.
- 알파벳으로 이루어진 수가 N개 주어졌을 때, 그 수의 합을 최대로 만드는 프로그램을 작성하시오.

```
ABC => 100A + 10B + C
BCD => 100B + 10C + D
```

**문제는 결국 주어지는 단어들을 더한 최대값을 구해야함** 

```python 
n = int(input()) 
word = [list(map(lambda x: ord(x)-65, input().rstrip())) for _ in range(n)] 
alpha = [0] * 26 

for i in range(n): 
  j = 0 
  for w in word[i][::-1]: 
    alpha[w] += (10 ** j) 
    j += 1 

alpha.sort(reverse=True) 
ans, t = 0, 9 

for i in range(26): 
  if alpha[i] == 0: 
    break 
    ans += (t * alpha[i]) 
    t -= 1 
    
print(ans)


```
