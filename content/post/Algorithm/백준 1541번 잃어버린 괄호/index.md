+++
author = "Hugo Authors"
title = "백준 1541번 잃어버린 괄호"
date = "2021-04-12"
description = "백준 1541_잃어버린 괄호 파이썬 문제풀이"
categories = [
    "Algorithm"
]
tags = [
    "백준", "boj", "python", "1541", "greedy"

]

image = "boj.png"

+++

# 1541번 잃어버린 괄호

[문제 보러가기](https://www.acmicpc.net/problem/1541)

## 🅰 코드

```python
# '-'부호로 나눠진 문자열 저장
arr = input().split('-')
# 결과 변수 생성
result = 0
# 처음 '-'부호가 나오는 부분까지 더하기
for i in arr[0].split('+'):
    result += int(i)
# 그 뒤엔 다 빼주는데 '+'부호로 묶인 것도 나눠서 빼기 → -(a+b) = -a-b
for i in arr[1:]:
    for j in i.split('+'):
        result -= int(j)

print(result)
```


## ✅ 후기

* 문제에 주어진 문자열에서 차례로 연산을 하기만 하면 되는 비교적 쉬운 문제였다고 생각했지만 중간에 한번 함정이 있어서 고민이 필요했다...
* 문제에서 요구하는 가장 최소의 값이 나오긴 위해서는 `-`부호 뒤에 오는 숫자들의 값이 커야 했으며 이를 표현하기 위해 `-`부호 뒤의 문자열에서  `+`부호로 나누어 각각을 빼주는 작업을 진행하였다.
* 평소 슬라이싱을 주로 사용했어서 비교적 쉽게 접근할 수 있었던 것 같다. 파이썬 조아😗