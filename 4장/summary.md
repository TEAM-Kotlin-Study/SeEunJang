:ghost: kotlin 4장 정리 :ghost:
=============
### 4.1 안드로이드 개발용 코틀린 사용 
-------------
* kotlin은 자바를 대체하는 언어. 어떤 이유로? -> 안드로이드 버전으로 인해 자바로는 최신 기술을 이용할 수 가 없다. kotlin은 안드로이드 버전과
관계 없이 현대 언어의 장점을 사용할 수 있다!

### 4.4 기본 구문
-------------
* 변수와 상수 
  * 변수는 var, 상수는 val로 선언
  > var a: Int = 10 // var 변수명: 자료형 = 값   
  > val b: Int = 20 // val 변수명: 자료형 = 값   
  > :rocket:__코틀린은 자료형을 지정하지 않아도 형추론을 지원하여 자료형을 생략할 수 있다__:rocket:   
  > var a = 10   
  > var b = 20 
  * 변수는 값을 변경 가능, 상수는 불가능 val은 자바의 final 키워드에 대응한다.
    * 자바의 final 키워드: 변수를 선언과 동시에 초기화하며, 이후에 값 수정 불가능

* 함수
  * 일정 동작을 수행하는 특정 형식의 코드 뭉치.
  * 함수를 선언하는 방법
  > fun 함수명(인수1 : 자료형1 , 인수2 : 자료형2 ...): 반환 자료형    
  > 코틀린에서 반환값이 없을 때, Unit형을 사용한다. (자바의 void와 같음)   
  >   > fun greet (str: String): Unit {   fun greet(str: String): Unit   
  >   > &nbsp; &nbsp; printlin(str)   
  >   > }   
  >   > :rocket:__반환값이 Unit일 경우에는 반환 자료형을 생략할 수 있다.__:rocket:     
  >   > fun greet (str: String) {   
  >   > &nbsp; &nbsp; println(str)   
  >   > }   


### 4.5 기본 자료형 
-------------
* 기본 자료형 (코틀린의 기본 자료형은 모두 객체!)
  * 숫자형
    * Double    
    * Float   
    * long   
    * Int   
    * Short   
    * Byte   
  * 문자형
    * String("")  + 여러 줄에 걸친 문자열은 """ """   
    > 문자열 비교는 == 사용 (java의 equals() 메소드와 대응)
    * Char('')   
  * 배열
    * Array   
    * arrayOf() 메서드를 사용하여 배열의 생성과 초기화를 함께 수행
    > val numbers : Array<Int> = arrayOf(1,2,3,4,5)   
    > val numbers2 = arrayOf(1,2,3,4,5) //자료형을 유추할 수 있을 때는 생략 가능   
  
### 4.6 제어문 
-------------
  * if : 자바와 동일
  * when : 자바의 switch문에 대응. if문처럼 사용도 가능.
  > val x = 1   
  >   
  > when (x) {   
  >  &nbsp; 1 -> println("x == 1")   &nbsp; &nbsp; &nbsp;// 값 하나   
  >  &nbsp; 2,3 -> println("x == 2 or x == 3")   &nbsp; &nbsp; &nbsp;// 여러 값은 콤마로   
  >  &nbsp; in 4..7 -> println("4부터 7사이")  &nbsp; &nbsp; &nbsp; // in 연산자로 범위 지정   
  >  &nbsp; !in 8..10 -> println("8부터 10 사이가 아님")      
  >  &nbsp; else -> {                     &nbsp;     &nbsp;   &nbsp;    // 나머지    
  * for : 자바의 foreach와 비슷    
    * 다양한 사용   
    > 증가 범위 : .. 연산자 (ex: 1..3)   
    > 증감의 간격 : step 키워드   
    > 감소 범위 : downTo  키워드 (ex: 10 downTo 0)   
  * while , do while : 자바와 동일      
 
 ### 4.7 클래스
-------------
  * 클래스 선언 : 자바와 다르게 new 키워드 사용하지 않음
  * 생성자 : 생성자 초기화 코드 작성시, constructor로 생성자를 표현.   
    init 블록에 작성한 코드가 클래스를 인스턴스화할 때 가장 먼저 초기화됨. constructor 대신 사용 가능.   
  * 프로퍼티 : 클래스의 속성을 사용하기 위해 멤버에 직접 접근하는 것   
    자바의 getter/setter 역할을 할 수 있음.      
  * 접근 제한자 : 변수나 함수를 공개하는 데 사용하는 키워드
   * public : 전채 공개 default 값   
   * private : 현재 파일 내부에서만 사용 가능   
   * internal : 같은 모듈 내에서만 사용할 수 있다   
   * protected : 상속받은 클래스에서 사용할 수 있다   
  * 클래스의 상속: 코틀린에서 클래스는 기본적으로 상속이 금지되어있다. 가능하게 하려면 open 키워드를 클래스 선언 앞에 추가.   
  * 내부 클래스 : inner를 사용. 내부 클래스는 외부 클래스에 대한 참조를 가지고 있음. 
  * 추상 클래스 : 미구현 메서드가 포함된 클래스. 클래스와 미구현 메소드 앞에 abstract 키워드를 붙임.   
  :bulb:추상 클래스는 직접 인스턴스화할 수 없고 다른 클래스가 상속하여 미구현 메서드를 구현해야 함.   
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;이때 추상 클래스는 open 키워드가 필요없음.:bulb:
  * 데이터 클래스 : 클래스 선언 앞에 data 키워드를 붙이면 getter, setter, toString(), equals(), hashCode()를 구현한 클래스를 간단하게 생성 가능. 작성할 때   
  기본 생성자에 var이나 val로 매개변수 1개 이상 있어야 함. 
  >
 ```javascript
class Person {
    String name;
    int age;
 }
  public String getName(){
        return name;
    }

    public void setName(String name){
        this.name = name;
    }
}
```
 이 코드를 data 클래스를 이용하면 한줄로 표현이 가능하다.    
  ```kotlin
 data class Person( val name: String, val age: Int )
 ```   
 * 구조 분해 : 프로퍼티를 순서대로 할당해 주는 기법   
 
### 4.8 인터페이스   
-------------
 인터페이스는 미구현 메서드를 포함하여 클래스에서 이를 구현. 다중 구현이 가능하고, 주로 클래스에 동일한 속성을 부여해 같은 메서드라도 다른 행동을 할 수 있게 사용.   
 *   인터페이스 구현 :     
   ```kotlin
 interface Runnable {   
   fun run()   
 }
 ```    
 인터페이스에 추상 메서드 포함 가능. 여기서는 abstract 키워드 필요없다. 이 인터페이스를 구현해보면      
   ```kotlin
 class Human : Runnable {
   override fun run(){
     println("달린다")
 }
 } 
 ```    
  
### 4.9 null 가능성    
-------------
기본적으로는 null 값 허용하지 않음. 따라서 모든 객체는 생성과 동시에 값을 대입하여 초기화를 해야 함. 허용하려면 별도의 연산자가 필요하다.   
 * null값을 허용하려면 자료형 옆에 ? 기호를 붙여주면 된다.    
 * lateinit 키워드 : 초기화를 나중에 해주고 싶다면 변수 선언 앞에 lateinit 키워드를 추가해주면 된다.    
 <lateinit 사용 가능 조건>   
   * var 변수 only   
   * null값으로 초기화 불가능   
   * 초기화 전에는 변수를 사용할 수 없다.   
   * Int, Long, Double, Float에서는 사용 불가능.   
 * lazy : 값을 변경할 수 없는 val을 사용. val에서만 사용가능하다.      
  ```kotlin
  val str : String by lazy {   
  println("초기화")    
  "hello"  // 초기화할 값 작성      
  }
  
  println(str) //초기화; hello     
  println(str) // hello    
 ```      
 * null 갑시 아님을 보증 : !!를 추가   
 * 안전한 호출 : ?. 연산자를 사용하면  null값이 아닌 경우에만 호출을 한다.    
 * 엘비스 연산자 : null이 아닌 기본값을 반환하고 싶을때 ?:   
 
    
### 4.10 컬렉션   
-------------
 컬렉션이란? 개발에 유용한 자료구조.    
 * 리스트 : 배열처럼 같은 자료형의 데이터들을 순서대로 가지고 있는 자료구조. 중복된 아이템들을 가질 수 있고, 추가, 삭제, 교체 등이 가능. 
   - 요소를 변경할 수 없는 읽기 전용 리스트는 listOf() 메서드       
   - 요소를 변경하는 리스트는 mutableListOf() 메서드      
 * 맵 : 키와 값의 쌍으로 이루어진 키가 중복될 수 없는 자료구조. 리스트와 마찬가지로 mapOf(), mutableMapOf() 메서드가 있다. 맵의 요소를 접근하기 위해선 대괄호 안에 
  키를 요소명으로 작성하여 접근한다.   
 * 집합 : 중복되지 않는 요소들로 구성된 자료구조. setOf() 메서드로 읽기 전용, mutableSetOf() 메서드로 수정 가능한 집합 생성.   
  
### 4.11 람다식   
-------------
 1. 람다식은 하나의 함수를 표현하는 방법으로 익명 클래스나 익명 함수를 표현하는 방법으로 익명 클래스나 익명 함수를 간결하게 표현할 수 있어서 매우 유용. 코드를 간결하게 해주는 장점이 있지만 디버깅이 어렵고 너무 많이 사용하면 오히려 가독성이 떨어짐.   
 2. 람다식은 항상 중괄호로 둘러싸여 있다. {인수 목록 -> 본문}   
 3. 람다식을 변수에 저장할 수 있고, 이러한 변수는 일반 함수처럼 사용할 수 있다.   
  * SAM 변환 : 
  
  
  
  
  
 
 
 
 
 
  
  
  
  
   
