# 기본 타입과 연산

- Byte, Short, Int, Long, Char, String, Float, Double, Boolean 기본 타입이 있다.
- String은 java.lang에 있고 나머지는 scala 패키지에 있다.
- java.lang과 scala는 모두 import하기 때문에 Int 처럼 그냥 쓰면 된다.
- `"""`는 raw 문자열을 위한 문법이다. raw 문자열안에 `|`를 쓰면 stripMargin 으로 문자열 앞에 공백을 없애준다.
- 심볼 타입 리터럴은 단어 앞에 단 따옴표를 붙여 표현한다. 동일한 심볼은 동일 한 객체를 참조한다. (intern)
  ```scala
  val s = 'aSymbol
  ```
- 기본 문자열 인터폴레이터는 `s`, `raw`, `f`가 있고 추가 가능하다.
- 전위, 중위, 후위 연산자를 지원하고 전위 연산자는 `+ - ! ~`만 쓸 수 있다. 메서드 이름은 `unary_-` 이런식으로 쓴다.
- 연산자가 일반 메서드인데 쇼트 서킷이 가능한 이유는 call by name 형식으로 호출 할 수 있기 때문이다.
- 스칼라 `==` 연산은 값 비교가 기본이고 객체 참조 비교를 하려면 `eq`를 써야 한다.
- 스칼라는 메소드 첫글자로 우선 순위를 정한다. 하지만 할당 연산자로 끝나는 `*=` 같은 경우는 첫글자가 아니고 할당 연산자의 우선순위를 가진다.
- 기본 타입은 암시적 변환으로 풍부한 래퍼 기능을 쓸 수 있다. (scala.runtime.RichByte 같은 클래스)
  ```scala
  0 max 5
  4 to 6
  ```
