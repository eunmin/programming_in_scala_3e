# 스칼라 첫걸음

- 스칼라에 프리미티브 타입 대응 클래스는 컴파일시 프리미티브 타입으로 변환되어 성능상 이점을 얻을 수 있다.
- 스칼라 문자열은 자바 String 클래스로 구현되어 있다. java.lang 타입은 간단한 이름으로 쓸 수 있다.
  ```scala
  val msg2: java.lang.String = "Hello again, world!"

  val msg3: String = "Hello yet again, world!"
  ```
- 함수 정의에 결과 타입을 생략해도 추론 가능 하지만 재귀 함수는 추론 불가능하기 때문에 명시해야한다.
- 추론이 가능한 경우라도 결과 타입을 명시하는 것이 코드를 읽기에 좋다.
- 부수 효과를 결과로 내는 함수는 Unit 타입을 쓰면 된다.
- 스칼라를 스크립트로 쓸 때 인자는 `args`라는 배열에 들어온다.
  ```scala
  println("Hello," + args(0) + "!")
  ```
- `++i`나 `i++`을 쓸 수 없다. `i = i + 1`을 쓰거나 `i += 1`을 써야한다.
- `if`나 `while`문 뒤에 조건식에 괄호는 생략할 수 없다.
- 스칼라 함수 리터럴 문법은 아래와 같다,
  ```scala
  (x: Int, y: Int) => x + y

  x => x + 1
  ```
- `foreach` 구문 뒤에 오는 함수에 인자가 하나라면 바로 사용할 수 있다.
  ```scala
  args.foreach(println)
  ```
