## 숨바꼭질 3 (13549)

> 너비우선탐색, 다익스트라

### 풀이

> recode.js

1. deque를 구현한다.
   - MAX의 두배 크기의 배열을 만들되,
   - 반으로 쪼갤 예정이므로, 반씩 쪼갠 각 배열에 +1, 쪼갠 각 배열 사이 값을 넣지 않을 칸을 위해 전체 배열에 +1 한 크기의 배열을 만든다.
   - back: `0 ~ Half - 1` 까지는 시간이 1초 걸리는 경우를 계산한 것
   - front: `Half + 1 ~ MAX`까지는 시간이 0초 걸리는 경우를 계산한 것
2. push 함수를 만든다.
   - front에 넣을 경우 half+1 부터 늘려가며
   - back에 넣을 경우 half-1 부터 줄여가며
   - deque에 값을 넣는다.
3. pop 함수를 만든다.
   - deque에 들어간 값들 중 제일 마지막 부터 앞으로 움직이며 값을 꺼내야 한다.
   - 따라서 back의 인덱스가 front의 인덱스보다 크면 null, 그렇지 않으면 현재 가장 마지막 인덱스의 값을 return한다.
4. 이동한 지점이 k가 될때까지
   - 순간이동할 경우 : front에 push, 시간계산 없음
   - 걸을 경우 : back에 push, 시간 + 1
   - k에 도착하면 도착지점까지 걸린 시간을 출력하고 반복문을 종료한다.

#### ✍ 유의사항

- 단순 bfs로 푸는 문제가 아니다.
  - 모든 간선의 가중치가 같아야만 bfs의 의미가 있다.
  - 이 문제는 간선이 0 또는 1로 갈리기 때문에 단순 bfs로 풀면 안된다.
- deque으로 푸는 것이 훨씬 빨랐다.
  - 아무래도 십만개가 될 수 있는 배열을 shift하려니 시간이 오래 걸렸다.
