# 함수형 객체

- 클래스를 선언할 때 이름 뒤에 파라미터를 선언할 수 있는데 이를 클래스 파라미터라고 한다. 이 파라미터로 클래스를 생성할 수 있는 주 생성자를 만든다.
  ```scala
  class Rational(n: Int, d: Int)
  ```
- 자바 처럼 `toString`을 오버라이드 할 수 있다.
  ```scala
  class Rational(n: Int, d: Int) {
    override def toString = n + "/" + d
  }
  ```
- 클래스 생성시 선행 조건은 `require`로 지정할 수 있다. `require` 조건에 맞지 않으면 생성시 `InllegalArgumentException`이 발생한다.
  ```scala
  class Rational(n: Int, d: Int) {
    require(d != 0)
    override def toString = n + "/" + d
  }
  ```
- 다른 생성자(보조 생성자)는 메서드 이름이 `this`이고 인자를 다르게 하면된다. 보조 생성자는 항상 다른 생성자를 불러야 한다. (결국 어디선가 주 생성자를 부르게 된다.)
- 슈퍼 클래스의 생성자는 주 생성자만 부를 수 있다.
- 스칼라 코드에서 `$`는 사용할 수 없다.
- 상수 이름은 첫글자만 대문자로 표시한다. `XOffset`
- 리터럴 식별자를 쓰면 예약어도 쓸 수 있다. Thread.\`yield\`()
- 암시적 변환 메서드는 스코프 안에 있어야 쓸 수 있다.
  ```scala
  implicit def inToRational(x: Int) = new Rational(x)
  ```
