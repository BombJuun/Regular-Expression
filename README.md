# Regular-Expression

👉**정규표현식이란?**

정규표현식은 문자열에서 특정한 규칙을 가지는 문자열의 집합을 표현하기 위한 형식 언어이다.

👉**사용하는 이유**

복잡하고 특정한 규칙을 가진 문자열을 처리할 때 사용한다.

예를 들어 전화번호 뒷자리를 \*로치환시키는 프로그램을 정규표현식을 사용하지 않고 구현하기가 쉽다. 

하지만 전화번호 뒷자리가 아닌 문자열이 규모가 방대하고 복잡하다면 어떨까?  

치환프로그램은 더 구현하기가 어려워지고 코드가 복잡해질 것이다.

이러한 단점을 해소해 줄 수 있는 것은 정규표현식.

정규표현식을 사용하면 빠른 구현과 간결해진 코드를 볼 수 있다.

👉**특징**

1.정규표현식은 많은 텍스트 편집기와 프로그래밍 언어에서 문자열의 검색과 치환을 위해 지원하고 있으며,표현식 자체의 문법도 여러가지 존재
		(사용되는 언어마다 문법이 조금씩 다를수 있음)

2.텍스트 처리 프로그램,텍스트 편집기, 프로그래밍 언어에서 정규표현식 기능을 제공

3.**내장 되어있는 프로그래밍 언어**:펄,JavaScript,루비,Tcl

**표준 라이브러리로 사용하는 프로그래밍 언어**:

.Net FrameWork,Java,Python,POSIX,C,C++등

**그 밖의 언어**:별도의 라이브러리 사용

4.정규표현식의 활용:검색 엔진,워드 프로세서와 문서 편집기의 찾아바꾸기 대화상자,어휘 분석 등

**👉패턴**
	
특정 목적을 위해 필요한 문자열 집합을 지정하기 위해 쓰이는 식이다.
문자열의 유한 집합을 지정하는 단순한 방법은 문자열의 요소나 멤버를 나열하는 것이다.
 
ex)정규 표현식 p.에서 p는 문자 그대로로 해석되며 .은 줄바꿈을 제외한 모든 문자와 일치시키는 메타 문자이다.

**👉메타문자란?**


다른 언어에서 연산자나 예약어로 쓰이는 문자를 정규 표현식에서는 메타 문자라고 부른다. 	메타 문자로 된 자원을 찾아야하는 경우에는 \(역슬래시)를 사용하여 탈출하면 된다.
파이썬 re모듈의 메타문자는 \^$.|[]()*+?{} 로 구성되어 있다.

	1)불리언 "또는" |:수직선은 여러 항목 중 선택하기 위해 구분
	ex)gray|grey는 "gray"또는 "grey"와 일치한다.
	
	2)그룹묶기():괄호를 사용하면 연산자의 범위와 우선권을 정의
	ex) gray|grey와 gr(a|e)y는 "gray"또는 "grey"와 일치한다.

	3)양의 지정:
		?:물음표는 앞문자를 사용하거나 않거나를 의미
		ex)colou?r는 color 또는 colour를 일치 시킴

		*:별표는 앞 문자를 0번이상 발생
		ex)av*c는 "ac","avc","avvc","avvvc","avvvvvc"등을 일치 시킴

		+:덧셈 기호는 1번 이상의 발생
		ex)av+c는 "avc","avvc","avvvc","avvvvvc"등을 일치 시키나 "ac"는
			일치시키지 않음
		
		{n}:정확히 n번 만큼 일치
		{min,}: min번 이상 만큼 일치
		{min,max}:적어도 min번 만큼 일치시키지만  max번 만큼 초과하여 
			일치시키지 않은다.
	4)\n:일치하는 패턴들 중 n번째를 선택하며,n은 1에서 9중 하나가 올수 있음

	
	5)[^]:문자 클래스 안의 문자를 제외한 나머지를 선택
	ex)[^abc]d는 ad,bd,cd는 포함하지 않는다.

	6)[]:"[","]"사이의 문자 중 하나를 선택 |를 여러개 쓴 것과 같은 의미
	ex)[abc]d는 ad,bd,cd를 뜻한다.
	ex)[a-z]는 a부터 z까지 중하나

	
**👉인식 타입**

	표현식(규칙)	뜻
	\s		공백(space) 한 개
	\w		문자 or 숫자 한 개
	\W		문자 or 숫자가 아닌 것
	\d		숫자 한 개
	\D		숫자가 아닌 문자 한 개
	.		모든 문자 한 개
	^		문자열 시작
	$		문자열 끝

**👉파이썬에서의 사용방법**

내장 모듈인 re를 사용하여 표현한다.

**①**

	match(패턴,문자열,플래그)

-문자열의 처음부터 시작해서 작성한 패턴이 일치하는지 확인

**②**

	search(패턴,문자열,플래그)

-match와 유사하지만 패턴이 문자열의 처음부터 일치하지 않아도 된다.

**③**

	findall(패턴,문자열,플래그)

-문자열 안에 패턴에 맞는 케이스를 전부 찾아서 리스트로 반환한다.

**④**

	finditer(패턴,문자열,플래그)

-findall과 비슷하지만 리스트가 아닌 iterator형식으로 반환한다

**⑤**

	fulmatch(패턴,문자열,플래그)

-문자열에 시작과 끝이 정확하게 패턴과 일치할 때 반환한다.

**⑥**

	split(패턴,문자열,최대 split 수,플래그)

-문자열애서 패턴이 맞으면 이를 기점으로 리스트로 쪼개는 함수이다. 만약 최대 split수를 지정하면 문자열을 지정한 수 만큼 쪼개고 그 수가 도달하면 쪼개지 않는다.

**⑦**

	sub(패턴, 교체할 문자열, 문자열, 최대 교체 수, 플래그)

-문자열에 맞는 패턴을 교체할 문자열로 교체한다.
최대 교체수는 split의 최대 split수와 동일

**⑧**

	subn(패턴, 교체할 문자열, 문자열, 최대 교체 수, 플래그)

-sub와 동작은 동일하지만 반환  결과가 (문자열,매칭횟수)형태로 반환한다.

**⑨**

	compile(패턴, 플래그)

-만약 패턴과 플래그가 동일한 정규식을 여러번 사용하려면 compile()를 사용하여 지정한 다음, 위의함수들을 사용할 수 있다.

**⑪**

	purge()

-compile()로 만들어 놓은 객체는 캐시에 100개까지 저장된다고 알려져 있으며 그 수를 넘어가면 초기화가 된다
purge()를 호출하면 100개가 넘어가지 않아도 캐시를 초기화하는 함수이다.

**⑫**

	escape(패턴)

-패턴을 입력 받으면 특수문자들에 이스케이프 처리를 한 다음 반환한다.

**👉match object method()**

finall()를 제외하고 모든 함수들의 반환은 match object로 반환되는데 match object 에서는 group(),start(),end()등과 같이 찾은 패턴이 문자열의 위치나 매칭 문자열을 반환하는 함수를 제공한다.


	group():패턴에 맞는 문자열을 추출
	start():문자열에서 어디부터 패턴에 맞는 문자가 시작했는지 반환
	end():어디까지인지 반환
	span():시작과 끝 반환
	
**👉코드 예제(Python)**
```python
# 전화번호 유효성 검사 예제 
import re

def validate_phone_number(phone_number):
    pattern = r'^\d{3}-\d{3,4}-\d{4}$'
    # r': raw String의미, 백슬래시(\)를 이스케이프하지 않고 그대로 처리하기 위해 사용됩니다.
    # \d{3}:숫자 세 자리 뒤에는 하이픈(-)이 위치해야 합니다.
    # \d{3,4}. 하이픈 뒤에는 숫자 세 자리 또는 네 자리가 위치
    # \d{4}. 하이픈 다음에는 숫자 네 자리가 위치해야 합니다.
    # $:문자열 끝을 
    # 예시 유효한 전화번호: 010-1234-5678, 02-987-6543
    # 예시 유효하지 않은 전화번호: 123-4567, 010-12345-6789, 02-1234-5678

    if re.match(pattern, phone_number):
        return True
    else:
        return False


phone_number1 = "010-1234-5678"
phone_number2 = "02-987-6543"
phone_number3 = "123-4567"
phone_number4 = "010-12345-6789"
phone_number5 = "02-1234-5678"

print(validate_phone_number(phone_number1))  # 출력: True
print(validate_phone_number(phone_number2))  # 출력: True
print(validate_phone_number(phone_number3))  # 출력: False
print(validate_phone_number(phone_number4))  # 출력: False
print(validate_phone_number(phone_number5))  # 출력: False


```

출처:[위키피디아](https://ko.wikipedia.org/wiki/%EC%A0%95%EA%B7%9C_%ED%91%9C%ED%98%84%EC%8B%9D),
[위키독스](https://wikidocs.net/4308),
[chat GPT](https://chat.openai.com/)
