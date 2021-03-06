## 물병(1052)

> 시뮬레이션

### 풀이

1. 물병을 최대한 합칠 수 있는 만큼 합친다.

   N=1 : [1] => [1]

   N=2 : [1, 1] => [2]

   N=3 : [1, 1, 1] => [2, 1]

   N=4 : [1, 1, 1, 1] => [2, 2] => [4]

   N=5 : [1, 1, 1, 1, 1] => [2, 2, 1] => [4, 1]

   N=6 : [1, 1, 1, 1, 1, 1] => [2, 2, 2] => [4, 2]

   N=7 : [1, 1, 1, 1, 1, 1, 1] => [2, 2, 2, 1] => [4, 2, 1]

   N=8 : [1, 1, 1, 1, 1, 1, 1, 1] => [2, 2, 2, 2] => [4, 4] => [8]

   ...

   결과적으로 2의 제곱수라면 무조건 합칠 수 있다.
   반대로 2의 제곱수가 아니라면 반드시 상점에서 물을 사야한다.

2. 이진법 계산이 가능하다.

   > 2로 나눌때마다 1이 남는다 ? 물병을 합치고 **남은 물병**이라는 말
   > 다시 말하면, N을 이진수로 표현했을때 나오는 1의 개수가 남는 물병의 개수와 같다.
   > 단, 다 합치고 남은 물병들의 개수가 K를 넘으면 안된다.

   따라서 다 합치고 남은 물병 개수가

   - K보다 크다면? N을 하나씩 추가한다. => 상점에서 물병을 구매했다는 의미
   - K와 같거나 작다면? 상점에서 물병을 몇개 구매했는지 출력한다. => (N - 초기 N값)을 해주면 된다.

#### 🤦‍♀️ 개인적으로 아쉬웠던 점

1. 문제를 제대로 이해하지 못했다.
   - 물병은 "같은 양"의 물끼리만 합칠 수 있다.
2. 규칙을 제대로 파악하지 못했다.
   - 1번을 제대로 이해하지 못했으니.. 당연히 이 부분도..
3. 정답이 없으면 -1을 출력하라고 하였는데, 나는 상점에 갈 필요가 없으면 -1을 출력하라는 의미인 줄 알았다.
   - 하지만 아니었던 것 같다... 해당 조건을 없애주니 통과했다.

**※ 참고한 블로그** - [[백준] 1052 :: 물병](https://qgqg264.tistory.com/57)
