## 사탕 게임(3085)
> 브루트포스

### 풀이
1. 사탕을 교환할 두 자리를 선정한다. 
   - 모든 좌표를 돌면서
   - 인접한 사탕이면서 서로 색이 다른 것이 있는지 확인한다
   - 인접 && 서로 색이 다른 사탕이면 사탕을 서로 교환한다. 
2. 색이 같은 사탕끼리 줄지어진 행 또는 열을 탐색한다. 
   - **행 또는 열**에서 같은 색의 사탕이 가장 많았을 떄를 구한다. 
3. 최댓값을 출력한다. 

#### 🤦‍♀️ 나의 시행착오
1. 문제를 잘못 이해했다. 
   - 행 또는 열을 탐색해야 하는데, **인접한 같은 색의 사탕 중 가장 긴 경우**를 구하느라, 전체 그래프에서 dfs로 탐색하며 찾았다. 
 