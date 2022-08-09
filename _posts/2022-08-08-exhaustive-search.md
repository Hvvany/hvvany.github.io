---
layout: single
title: "[22.08.08] Exhaustive Search"
---
# 완전 탐색1

#완전탐색 #exhaustive_search 

1. ## 무식하게 풀기(Brute-force)

   >  모든 경우의 수를 탐색하여 문제를 해결하는 방식

   - `부르트 포스`라고도 하며, 무식하게 밀어붙인다는 뜻
   - 가장 단순한 풀이 기법이며, `단순 조건문과 반복문`을 이용해서 풀 수 있다.
   - 복잡한 알고리즘 보다는, 아이디어를 어떻게 코드로 규현할 것인지가 중요하다.

   > 블랙잭 문제 예시

   ```python
   def blackjack(n, m, cards):
   max_total = 0 # 현재 가장 큰 합
   
   # 완전탐색(Brute-force)
   for i in range(n - 2):
   	for j in range(i + 1, n - 1):
   		for k in range(j + 1, n):
   			total = cards[i] + cards[j] + cards[k]
   			# 현재 가장 큰 합보다는 크고, m을 넘지 않아야 갱신
   			if max_total < total <= m:
   				max_total = total
   			# 합과 m이 같으면 더이상 탐색하는 의미가 없으므로 종료
   			if total == m:
   				return total
   return max_total
   ```

   > 3중 for문으로 해결

   

2. ## 델타 탐색(Delta Search)

   > (0,0)에서부터 이차원 리스트의 모든 원소를 순회하며 각 지점에서 상하좌우에 위치한 다른 지점을 조회하거나 이동하는 방식이다.

   > 이차원 리스트의 인덱스(좌표)의 조작을 통해서 상하좌우 탐색을 한다.
   >
   > 이때 행과 열의 변량인 -1, +1을 `델타값`이라 한다.
   >
   > | (0,0) | (0,1) | (0,2) |
   > | :---: | :---: | :---: |
   > | (1,0) | (1,1) | (1,2) |
   > | (2,0) | (2,1) | (2,2) |

   ```python
   # 1) 행을 x, 열을 y로 표현
   dx = [-1, 1, 0, 0]
   dy = [0, 0, -1, 1]
   
   # 2) 행을 r, 열을 c로 표현
   dr = [-1, 1, 0, 0]
   dc = [0, 0, -1, 1]
   ```

   ```python
   # 상(x-1, y)
   nx = x + dx[0]
   ny = y + dy[0]
   # 하(x+1, y)
   nx = x + dx[1]
   ny = y + dy[1]
   # 좌(x, y-1)
   nx = x + dx[2]
   ny = y + dy[2]
   # 우(x, y+1)
   nx = x + dx[3]
   ny = y + dy[3]
   ```

   ```python
   # 1. 델타값을 이용해 상하좌우 이동
   for i in range(4):
   nx = x + dx[i]
   ny = y + dy[i]
   
   # 2. 범위를 벗어나지 않으면 갱신
   if 0 <= nx < 3 and 0 <= ny < 3:
   x = nx
   y = ny
   ```

   > 상하좌우로 이동 후 범위를 벗어나지 않는지 확인 및 갱신

   - 이차원 리스트의 상하 좌우 탐색 정리

   ```python
   # 1.델타값 정의(상하좌우)
   dx = [-1, 1, 0, 0]
   dy = [0, 0, -1, 1]
   
   # 2.이차원 리스트 순회
   for x in range(n):
   	for y in range(m):
       
   		# 3.델타값을 이용해 상하좌우 이동
   		for i in range(4):
   			nx = x + dx[i]
   			ny = y + dy[i]
               
   			# 4.범위를 벗어나지 않으면 갱신
   			if 0 <= nx < n and 0 <= ny < m:
   				x = nx
   				y = ny
   ```

   - 상하좌우+대각선 8방향 델타값

   ```python
   # 상, 하, 좌, 우, 좌상, 좌하, 우상, 우하
   dx = [-1, 1, 0, 0, -1, 1, -1, 1]
   dy = [0, 0, -1, 1, -1, -1, 1, 1]
   ```

   
