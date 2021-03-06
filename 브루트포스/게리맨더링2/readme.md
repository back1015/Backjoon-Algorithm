## 게리맨더링2 (17779)

> 브루트포스

### 풀이

1. 기준점이 될 수 있는 x, y를 고른다.
2. 경계의 길이가 될 수 있는 d1, d2를 고른다.
3. 기준점과 경계의 길이값을 통해 구역 `5`의 경계선을 그린다.
4. 나머지 구역(1, 2, 3, 4)을 채워넣는다.
5. 구역별 인구수의 합을 구한다.
6. 최대 인구수와 최소 인구수의 차이를 구한다.
7. 인구수 차이의 최솟값을 구한다.

큰 개요는 위와같이 짜고, 다음과 같은 과정을 구성했다.

1. (1,1) ~ (n,n) 까지 가능한 모든 x, y를 고른다.
   - 고른 x, y값을 가지고 가능한 d1, d2를 구할 것이다.
2. d1, d2가 될 수 있는 모든 값들을 구한다.
   - ` if (x < x + d1 + d2 && x + d1 + d2 <= n && 1 <= y - d1 && y - d1 < y && y < y + d2 && y + d2 <= n)` 에 만족하는 경우, 배열에 넣는다.
   - 이 값들이 현재 1번에서 고른 기준점 (x, y)일때 가능한 경계의 길이값이다.
3. 2번에서 구한 각 d1, d2를 이용하여
   - 구역을 표시할 2차원 배열을 만든다: 나는 `area` 배열을 만들었고, 모든 값을 0으로 초기화해주었다.
   - `area`에 구역 `5`를 표시한다.
     - 경계선이 되는 칸에 대하여 dfs를 돌린다.
     - 경계선이 되는 칸의 값을 5로 바꿔준다.
4. 1, 2, 3, 4번 구역 표시를 해준다.
   - 3번에서 만든 `area`에 1, 2, 3, 4 구역을 표시해준다.
   - 단, 5번 구역을 침범해선 안된다.
   - 따라서 나는 1, 3번 구역은 왼쪽에서부터, 2, 4번 구역은 오른쪽에서부터 값을 채워나가는 방식으로 구현했다.
   - 채워가던 중 `area` 값이 5이면 break를 해줌으로써 5번 구역을 침범하지 않게 했다.
5. 구역별 인구수를 구한다.
   - `area`에 표기된 구역에 따라 인구수를 더해준다.
   - 인구수가 가장 많은 구역과 가장 적은 구역을 구한다.
   - 인구수의 차이를 구한다.
6. 인구수 차이의 최솟값을 구한다.
   - 해당 값을 출력한다.
