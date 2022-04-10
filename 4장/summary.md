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
  > :rocket: __코틀린은 자료형을 지정하지 않아도 형추론을 지원하여 자료형을 생략할 수 있다__ :rocket:   
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
  >   > :rocket: __반환값이 Unit일 경우에는 반환 자료형을 생략할 수 있다.__ :rocket:     
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
    
  
  
  
  
   
