[문제 설명]
1차원 배열로 부터 겹치지 않는 원소를 최대수 n/2로 구하기

[문제 접근 방식]
생각하지 못함...

[풀이 시간]
못풀었다...

[왜 못했나요?]
set을 생각하지 못했다...

[코드]

```
def solution(nums):
    # n은 항상 짝수
    # 결과의 최댓값은 n/2
    # nums는 1차원 배열
    # nums = [n1, n2, n3 ...] <= 10,000
    # 1 <= n <= 200,000
    # 1 <= 종류번호 <= 200,000
    # ***결과는 종류 개수의 최대값 하나***
    # 선택하는 방법은 n1-n2, n1-n3... + n2-n3, n2-n4...
    # ===> i = i + 1 until i = len(nums) - 1
    # 0,1 0,2 0,3 / 1,2 1,3 / 2,3
    # 배열 nums가 매개변수로 주어질 때, 선택하는 방법 중, 가장 많은 종류의 폰켓몬을 선택하는 방법 찾기??
    
    result = []
    for i in range(len(nums)):
        for j in range(len(nums)-1):
            if (i >= j) & (nums[i] is not nums[i+j]):
                result.append(nums[i])
      
    print(len(result))
    answer = len(result)
    return answer

nums = [3, 2, 4]
solution(nums)
```
