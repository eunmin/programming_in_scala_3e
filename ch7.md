# 내장 제어 구문

- 스칼라는 내장 제어 구문이 if, while, for, try, match 밖에 없다.
- while이나 do-while 문의 결과 값은 Unit 타입의 Unit 값 `()`이다.
- 스칼라에서 할당(=)의 결과는 Unit 값인 `()` 이다.
- `for` 구문에 사용하는 `<-`는 제너레이터라고 부른다.
- `for` 구문안에서 할당(=)을 써서 변수를 바인딩 할 수 있다.
- 예외를 던질 때 사용하는 `throw` 구문은 결과가 Nothing 타입이다.
- 예외를 잡을 때 사용하는 `catch` 구문은 match와 비슷하게 생겼다.
  ```scala
  try {
    val f = new FileReader("input.txt")
  } catch {
    case ex: FileNotFoundException => //...
    case ex: IOException => //...
  }
  ```
- `finally`를 사용하는 대신 `loan pattern`을 사용할 수 있다.
- `finally`에 결과 값은 버려진다. `return`을 하면 값을 던질 수 있긴 하다.
- 패턴 매치 표현식의 결과는 값이다.
- 스칼라에 break, continue 문법은 없다.
- scala.util.control에 Breaks 클래스에 있는 break 메소드를 쓸 수 있다.
  ```scala
  import scala.util.control.Breaks._
  import java.io._

  val in = new BufferedReader(new InputStreamReader(System.in))

  breakable {
    while(true) {
      println("? ")
      if (in.readLine() == "") break
    }
  }
  ```
- Breaks 클래스에 break 메서드는 예외를 던지고 breakable에서 잡는 형식으로 만들어져있다.
