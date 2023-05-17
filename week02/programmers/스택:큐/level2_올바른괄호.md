[문제 설명]
괄호가 바르게 짝지어졌다는 것은 '(' 문자로 열렸으면 반드시 짝지어서 ')' 문자로 닫혀야 한다는 뜻입니다. 예를 들어

"()()" 또는 "(())()" 는 올바른 괄호입니다.
")()(" 또는 "(()(" 는 올바르지 않은 괄호입니다.
'(' 또는 ')' 로만 이루어진 문자열 s가 주어졌을 때, 문자열 s가 올바른 괄호이면 true를 return 하고, 올바르지 않은 괄호이면 false를 return 하는 solution 함수를 완성해 주세요.

[문제 접근 방식]
원소의 수로 비교하려고 함

[풀이 시간]
틀림

[왜 못했나요?]
갯수로 비교했기 때문에 다음과 같이 닫는 괄호가 먼저 나오는상황')))((('에서 틀린답을 출력하게 되었다.
스택처럼 LIFO 구조를 생각했어야했는데 단순히 카운팅만 생각해서 아쉽다

[코드]
```
def solution(s):
    left = "("
    right = ")"
    
    left_size = 0
    right_size = 0
    
    answer = True
    
    for i in range(len(s)):
        if(s[i] is left):
            left_size += 1
        elif(s[i] is right):
            right_size += 1
        
        if(left_size != right_size):
            answer = False
            
    if((s[0] != left) | (s[len(s)-1] != right)):
        answer = False
    
    return answer

s = "((((())))))))))(((((()"
solution(s)
```

[비슷한 접근방식의 정답]
```
def solution(s):
    answer = True
    count = 0
    
    for i in range(len(s)):
        if s[i] == "(":
            count += 1
        else:
            if count > 0:
                count -= 1
            else:
                return False
            
    if count > 0:
        return False
    return True
       

```

[다른사람의 풀이]

```
def is_pair(s):
    st = list()
    for c in s:
        if c == '(':
            st.append(c)

        if c == ')':
            try:
                st.pop()
            except IndexError:
                return False

    return len(st) == 0
```
