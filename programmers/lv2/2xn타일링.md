# 문제설명

가로 길이가 2이고 세로의 길이가 1인 직사각형모양의 타일이 있습니다. 이 직사각형 타일을 이용하여 세로의 길이가 2이고 가로의 길이가 n인 바닥을 가득 채우려고 합니다. 타일을 채울 때는 다음과 같이 2가지 방법이 있습니다.

타일을 가로로 배치 하는 경우
타일을 세로로 배치 하는 경우

직사각형의 가로의 길이 n이 매개변수로 주어질 때, 이 직사각형을 채우는 방법의 수를 return 하는 solution 함수를 완성해주세요.

제한사항
가로의 길이 n은 60,000이하의 자연수 입니다.
경우의 수가 많아 질 수 있으므로, 경우의 수를 1,000,000,007으로 나눈 나머지를 return해주세요.

<br>

내가 푼 문제

```java
class Solution {
    public int solution(int n) {
        int[] answer = new int[n];
        answer[0] = 1;
        answer[1] = 2;
        if(n <= 2) 
            return answer[n-1];
        
        for(int i = 2; i < n; i++) {
            answer[i] = (answer[i-1] + answer[i-2]) % 1000000007;
        }
        
        return answer[n-1];
    }
}
```

dp 문제를 잘 못 풀기 때문에 많은 문제를 풀어봐야겠다. 
