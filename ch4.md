# 클래스와 객체
- 부수 효과만을 위해 실행하는 메소드를 프로시저라고 한다.
- 마침표나 `+` 같은 중위 연산자는 줄 끝에 배치해야 세미 콜론을 생략할 수 있다.
- 스칼라 클래스에는 정적 멤버가 없다.
- 싱글톤 객체와 클래스 이름이 같을 때 싱글톤 객체를 동반 객체라고 한다.
- 동반 객체와 클래스는 상대방의 비공개 멤버에 접근할 수 있다.
- 싱글톤 객체는 타입을 정의하지 않는다.
- 싱글톤 객체는 슈퍼클래스를 확장하거나 트레이트를 믹스인 할 수 있고 그런 싱글톤 객체는 슈퍼클래스나 트레이트 타입을 가질 수 있다.
- 싱글톤 객체의 초기화는 어떤 코드가 그 객체에 처음 접근할때 일어난다.
- 동반 클래스가 없는 싱글톤 객체를 독립 객체라고 한다.
- `println`은 `Predef.println`이고 이것은 `Console.println`이다.
- `fsc`라는 스칼라 컴파일러 데몬으로 컴파일 하면 빠르다.
- `main` 메서드가 정의된 스칼라는 `scala`로 실행할 수 있다.
- 싱글톤 뒤에 `extends App`으로 `App` 트레이트를 믹스인 하면 `main` 함수 없이 바로 실행할 수 있다. 인자는 `args` 변수로 접근할 수 있다.
  ```scala
  import ChecksumAccmulator.calculate

  object FallWinterSpringsSummer extends App {
    for (season <- List("faill", "winter", "string"))
      println(season + ": " + calculate(season))
  }
  ```
