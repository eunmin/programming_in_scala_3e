# 스칼라 두 번째 걸음

- 객체를 인스턴스화할 때, 값과 타입을 파라미터로 넘길수 있다. 이것을 파라미터화라고 한다.
- 타입은 각괄호 사이에, 값은 괄호 사이에 지정한다.
  ```scala
  val big = new java.math.BigInteger("12345")
  val greetStrings = new Array[String](3)
  ```
- 타입을 파라미터화 한것은 타입의 일부지만 값을 파라미터화 한것은 타입의 일부가 아니다.
- 배열은 변경 가능하다.
- 메소드가 파라미터를 하나만 요구하는 경우 점(.)과 괄호 없이 호출 할 수 있다.
  ```scala
  0 to 2
  (0).to(2)
  ```
- 점(.)과 괄호를 생략하려면 항상 호출 대상을 명시해야 한다.
  ```scala
  println 10 // error!!!
  Console println 10
  ```
- 변수 뒤에 괄호를 호출 하면 `apply` 메소드가 실행된다.
  ```scala
  greetStrings(i)
  greetStrings.apply(i) // 위와 같다
  ```
- 변수 뒤에 괄호를 쓴 구문에 할당하면 `update` 메소드가 실행된다.
  ```scala
  greetStrings(0) = "Hello"
  greetStrings.update(0, "Hello") // 위와 같다
  ```
- 타입에 괄호를 호출하면 `apply`라는 팩토리 메소드가 호출된다. 이 메서드는 동반 객체에 정의된다.
  ```scala
  val numNames = Array("zero", "one", "two")
  ```
- 변경 불가능한 시퀀스를 위해 `List`를 클래스를 사용할 수 있다.
  ```scala
  val oneTwoThree = List(1, 2, 3)
  ```
- `:::`은 두 리스트를 붙인다.
  ```scala
  val oneTwo = List(1, 2)
  val threeFour = List(3, 4)
  val oneTwoThreeFour = oneTwo ::: threeFour
  ```
- `::`는 리스트 앞에 항목을 추가한다. (`Cons`라고 부른다)
  ```scala
  val twoThree = List(2, 3)
  val oneTwoThree = 1 :: twoThree
  ```
- 메소드 이름이 콜론(:)으로 끝나면 오른쪽 피연산자에 대해 호출을 한다.
  ```scala
  1 :: twoThree
  twoThree.::(1) // 위와 같다
  ```
- 빈리스트는 `Nil`로 표현한다.
- `:+`로 리스트 뒤에 추가할 수도 있지만 리스트 크기 만큼 시간이 걸린다. 효율적으로 추가하려면
  `ListBuffer`를 쓰는 것이 좋다.
- 튜플은 점(.) 밑줄 다음에 1부터 시작하는 인덱스로 참조할 수 있다.
  ```scala
  val pair = (99, "Luftballons")
  pair._1
  pair._2
  ```
- Tuple 타입은 Tuple22까지 지원한다.
- Set 타입은 변경 가능한 타입과 변경 불가능한 타입이 있다. 변경 불가능한 타입이 기본이고 변경 가능한 버전을
  쓰려면 `import` 해야한다.
  ```scala
  import scala.collection.mutable

  val movieSet = mutable.Set("Hitch", "Poltergeist")
  movieSet += "Shrek" // 변경
  ```
- Map 타입도 Set 타입과 같이 변경 가능한 타입과 불가능한 타입이 있다. 역시 변경 불가능한 타입이 기본이다.
- Map 값을 표현할 때 어떤 값에 `->` 메소드를 사용해서 호출하면 그 값을 키로하는 튜플이 생긴다.
  ```scala
  val romanNumeral = Map(
    1 -> "I", 2 -> "II", 3 -> "III", 4 -> "IV", 5 -> "V"
  )
  ```
