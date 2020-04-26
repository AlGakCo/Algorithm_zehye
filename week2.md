## 알파벳 

[1987](https://www.acmicpc.net/problem/1987)

- (0,0)부터 dfs로 이동을 시작한다
- 다음칸으로 이동할 수 있으면 해당 알파벳을 체크하고 재귀를 실행한 후 다시 알파벳 체크를 해제한다
- 이동 칸의 최대값을 저장한 변수를 출력

```python 
def solve(x, y, l): 
  global ans 
  ans = max(ans, l) 
  
  for d in range(4): 
    i, j = x + dx[d], y + dy[d] 
    if 0<=i<r and 0<=j<c and alpha[table[i][j]] == 0: 
      alpha[table[i][j]] = 1 
      solve(i, j, l+1) 
      alpha[table[i][j]] = 0 
      
r, c = map(int, input().split()) 
table = [list(map(lambda x: ord(x)-65, input().rstrip())) for _ in range(r)] 
dx, dy = (-1, 1, 0, 0), (0, 0, -1, 1) 
alpha = [0] * 26 
ans = 0 

alpha[table[0][0]] = 1 
solve(0, 0, 1) 

print(ans)
```


어려워서 다른 사람들 코드를 많이 참고했다.. 외워야할듯!<br>
+ 백트레킹 공부 
