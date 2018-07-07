## Python 자료형

#### 1. 기본 데이터 타입

- int, float, bool, None(=null) type으로 구성.
- 타입추론을 지원하므로 변수 선언 시 별도의 타입을 명시하지 않음.

```python
a = 5 		# int
b = 3.5		# float
c = false	# bool
d = None	# None
```



- 타입변경을 위한 타입생성자를 지원.

```python
a = 10.5
b = int(a)
print(b)
# 10 출력

# bool()의 경우 유의사항
# 인자가 숫자일 경우 0이면 false, 그외 모든 숫자는 true
# 인자가 문자나 컬렉션일 경우 문자가 비어있거나 아무런 요소가 없으면 false
a = bool(-1)		# true
b = bool(0)			# false
c = bool("")		# false
d = bool("string")	# true
```



- 복소수 지원. (단, i를 j로 표현)

```python
a = 3 + 2j
b = a.real			# 실수 (b = 3)
c = a.imag			# 허수 (c = 2)
d = a.conjugate()	# 켤레복소수 리턴 함수 (d = 3 - 2j)
```

