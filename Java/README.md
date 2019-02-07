1. JAVA에 관하여
1. 변수
   1. 상수와 리터럴(constant & literal)
      - 상수 : 값을 한번만 저자알 수 있는 공간으로써 반드시 선언과 동시에 초기화해야 하며, 그 후 부터는 상수의 값을 변경할 수 없다.
      - 리터럴 : 그 자체로 값을 의미하는 것
      
         ![](/img/java1.PNG)
1. 연산자
   1. 우선순위
   
   종류 | 연산자 | 우선순위
   ---- | ---- | ----
   단항 연산자 | ++ -- + - ~ ! (type) | 높음
   산술 연산자 | * / % + - << >>
   비교 연산자 | < > <= >= instanceof
   논리 연산자 | & \| ^  && \|\|
   삼항 연산자 | ?:
   대입 연산자 | = += -= *= /= %= <<= >>= &= ^=  \|= | 낮음
   
1. 객체지향
   * 클래스 : 객체를 정의해 놓은 것
   * 클래스로부터 객체를 만드는 과정을 인스턴스화라고 하며 그로부터 만들어진 객체를 그 클래스의 인스턴스라고 한다.
   * 변수와 메서드
   
   변수의 종류 | 선언위치 | 생성시기
   ---- | ---- | ----
   클래스변수 | 클래스영역 | 클래스가 메모리에 올라갈 때
   인스턴스변수 | 클래스영역 | 인스턴스가 생성되었을 때
   지역변수 | 클래스 영역 이외의 영역<br>(메서드, 생성자, 초기화 블럭 내부) | 변수 선언문이 수행되었을 때
   
   * JVM의 메모리 구조
   
   ![](/img/java2.png)
   
   1. 메서드 영역(method area)
      - 프로그램 실행 중 어떤 클래스가 사용되면 JVM은 해당 클래사의 클래스파일(*.class)을 읽어서 분석하여 클래스에 대한 정보(클래스 데이터)를 이곳에 저장한다. 이 때, 그 클래스의 클래스변수(class variable)들이 생성되는 공간이다.
   1. 힙(heap)
      - 인스턴스가 생성되는 공간. 프로그램 실행 중 생성되는 인스턴스는 모두 이곳에 생성된다. 즉, 인스턴스변수들이 생성되는 공간이다.
   1. 호출스택(call stack or execcution stack)
      - 호출스택은 메서드의 작업에 필요한 메모리 공간을 제공한다. 메서드가 호출되면, 호출스택에 호출된 메서드를 위한 메모리가 할당되며, 이 메모리는 메서드가 작업을 수행하는 동안 지역변수(매개변수 포함)들과 연산의 중간결과 등을 저장하는데 사용된다. 그리고 메서드가 작업을 마치면 할당되었던 메모리공간은 반환되어 비워진다.
   </br>
   
   * 기본형 매개변수 : 변수의 값을 읽기만 할 수 있다. (read only)
   * 참조형 매개변수 : 변수의 값을 읽고 변경할 수 있다. (read & write) ex) 배열도 참조형

## overloading & overriding
* 오버로딩(overloading)
   - 하나의 클래스 내에 이미 사용하려는 이름과 같은 이름을 가진 메서드가 존재하여 중복해서 사용할 경우. 메서드 이름이 같고 매개변수의 개수 또는 타입이 달라야 한다.
* 오버라이딩(overriding)
   - 상위 클래스에 존재하는 메소드를 하위 클래스에서 필요에 맞게 재정의하는 것을 의미한다. 부모클래스와 이름, 매개변수, 반환타입이 같아야하고 접근제어자는 조상클래스보다 좁은 범위로 변경할 수 없다.
   
* 오버라이딩 예제
```java
class BindingTest3{
 public static void main(String[] args) {
  Parent p = new Child();
  Child  c = new Child();
 
  System.out.println("p.x = " + p.x);
  p.method();
  System.out.println();
  System.out.println("c.x = " + c.x);
  c.method();
 }
}
 
class Parent {
 int x = 100;
 
 void method() {
  System.out.println("Parent Method");
 }
}
 
class Child extends Parent {
 int x = 200;
 
 void method() {
  System.out.println("x=" + x);  // this.x와 같다.
  System.out.println("super.x=" + super.x);
  System.out.println("this.x="  + this.x);
 }
}

출력 결과 : 

p.x = 100
x=200
super.x=100
this.x=200

c.x = 200
x=200
super.x=100
this.x=200
```
## 생성자

* 인스턴스 초기화할 목적으로 사용
* 생성자 조건
   1. 생성자의 이름은 클래스 이름과 같아야 한다.
   1. 생성자는 리턴값이 없다.
* 생성자는 new 할때 처음이자 마지막으로 한 번만 수행된다.
* 명시적 vs 묵시적
* 눈에 보인다 vs 눈에 보이지 않는다.
* this();  -> 다른 생성자 호출
* this() 키워드는 무조건 생성자 안에서 첫 번째에서만 사용이 가능하다.

## 패키지
* 서로 관련이 있는 클래스들의 묶음

## this, super, 메모리의 4원칙, 다형성 3대 발생원리
* this() -> 생성자 호출
* super() -> 상위 클래스의 생성자 호출

ex)
```java
Point3D(){

super();

system.out.println();

}
```
### 주의
* 생성자에서는 super나 this는 무조건 첫째줄에서 초기화 해줘야 한다. print문이 먼저 쓰일경우 에러
* 하나의 생성자에는 this나 super 둘 중 쓰일 경우엔 하나만 쓸 수 있다. 하나의 생성자에 두 개의 명령어를 동시에 사용할 수 없다.

* 메모리의 4 원칙
   - 생주부주 : 생성된 주소는 부모의 주소를 가르킨다.
   - 자생부생 : 자식이 생성되었다면 부모가 먼저 생성된다.
   - 자설부설 : 자식의 설계도가 올라가면 부모의 설계도도 존재한다.
   - 설공매사 : 설계도에 공개된 메서드만 사용가능하다.

* 다형성 3대 발생원리
   - 부타자참 : 부모의 타입으로 자식을 참조할 수 있다.
   - 부타자생 : 부모의 타입으로 자식 생성 가능
   - 부메자호 : 부모의 메서드로 자식의 메서드 호출 가능
   
## equals 메소드를 오버라이드 하는 모든 클래스에서 지켜야할 사항

1. 반드시 hashCode메서드를 오버라이드 해야한다. 그렇지 않으면 object.hashCode 메서드의 규칙 위반
1. 애플리케이션 실행 중에 같은 객체에 대해 한 번 이상 호출되더라도 hashCode 메서드는 같은 정수를 일관성 있게 반환해야 한다.
1. equals(Object)메서드의 호출 결과 두 객체가 동일하다면, 두 객체의 각각에 대해 hashCode메서드를 호출했을 때 같은 정수값이 나와야 한다.
1. equals(Object) 메서드 호출 결과 두 객체가 다르다고 해서 두 객체 각각에 대해 hashCode 메서드를 호출 했을 때 반드시 다른 정수값이 나올 필요는 없다. (그러나 같지 않은 객체들에 대해 hashCode 메서드에서 서로 다른 정수 값을 반환하면 성능향상에 좋다.)

```java
@Override
    public boolean equals(Object obj) {
        // TODO Auto-generated method stub
        Customer c = null;
        boolean check = false;
        
        if(obj == null){
            return false;
        }
        
        if(obj instanceof Customer){
            c = (Customer)obj;
            
            if(this.name.equals(c.name) && this.age == c.age){
                return true;
            }
        }
        return false;
    }   
    
    @Override
    public int hashCode() {
        // TODO Auto-generated method stub
        int hashCode = 100;
        
        hashCode = hashCode * 31 + age;
        hashCode = hashCode * 31 + name.hashCode();
        
        return hashCode;
    }
```

## Wrapper class

기본 자료형(Primitive data type)에 대한 클래스 표현을 Wrapper class 라고 한다. `Integer`, `Float`, `Boolean` 등이 Wrapper class 의 예이다. int 를 Integer 라는 객체로 감싸서 저장해야 하는 이유가 있을까? 일단 컬렉션에서 제네릭을 사용하기 위해서는 Wrapper class 를 사용해줘야 한다. 또한 `null` 값을 반환해야만 하는 경우에는 return type 을 Wrapper class 로 지정하여 `null`을 반환하도록 할 수 있다. 하지만 이러한 상황을 제외하고 일반적인 상황에서 Wrapper class 를 사용해야 하는 이유는 객체지향적인 프로그래밍을 위한 프로그래밍이 아니고서야 없다. 일단 해당 값을 비교할 때, Primitive data type 인 경우에는 `==`로 바로 비교해줄 수 있다. 하지만 Wrapper class 인 경우에는 `.intValue()` 메소드를 통해 해당 Wrapper class 의 값을 가져와 비교해줘야 한다.

### AutoBoxing (기본형 값을 래퍼 클래스의 객체로 자동 변환해 주는 것)

JDK 1.5 부터는 `AutoBoxing`과 `AutoUnBoxing`을 제공한다. 이 기능은 각 Wrapper class 에 상응하는 Primitive data type 일 경우에만 가능하다.

ex1)
```java
List<Integer> lists = new ArrayList<>();
lists.add(1);
```
ex2)
```java
Integer num = 123;
bClass = boo; -> 자동적으로 됨
<br />
bClass = new Boolean(b) -> 처럼 할 필요가 없음
```

우린 `Integer`라는 Wrapper class 로 설정한 collection 에 데이터를 add 할 때 Integer 객체로 감싸서 넣지 않는다. 자바 내부에서 `AutoBoxing`해주기 때문이다.

### UnBoxing
```java
Boolean bClass = new Boolean(true);
boo = bClass; -> 자동적으로 됨. 1.6버전부터

boolean boo = (boolean)bClass; -> 예전엔 이렇게 했어야 했음(형변환을 직접 입력)
```
## SingleTon 패턴
각 종 설정 등이 저장된 클래스가 하나 있다고 치자. 프로그램 내에서 여기저기서 접근해서 설정을 바꾸기도 하고 값을 가져오기도 한다. 이런 클래스는 인스턴스를 하나만 가져야 한다. 하나 만들어서 쓰는 곳마다 인자로 전달해주면 되지만 접근해는 곳이 많다면 계속 인자로 전달하는 것은 그다지 비효율적이다. 전역변수처럼 어디에서나 인스턴스에 접근을 하면 좋겠다. 그래서 만들어진 패턴이 SingleTon 패턴이다. 이 패턴을 이용하면 하나의 객체를 만들어서 어디에서나 접근 가능하다.
http://smilennv.blog.me/220453798336

* SingleTon 패턴의 3가지 원리
   1. private 멤버 변수로 자기 자신의 클래스의 인스턴스를 가진다.
   1. private 생성자를 지정하여, 외부에서 절대로 인스턴스를 생성하지 못하게 한다.
   1. getInstance()메서드를 통해 객체를 static하게 가져오게 한다.

이는 유일한 인스턴스를 만들기 위해 생긴 규약이다. 또 하나는 상속이 불가능함, private 생성자 때문에 둘다 인스턴스를 1개만 가지도록 하는 원칙을 지킴

## Collection Framework
- 데이터 군을 저장하는 클래스들을 표준화한 설계

* List - 순서가 있는 데이터의 집합, 데이터의 중복을 허용한다.
   - ex) ArrayList, LinkedList, Stack, Vector Queue
* Set - 순서를 유지하지 않는 데이터의 집합, 데이터의 중복을 허용하지 않는다.
* Map - 키(Key)와 값(Value)의 쌍으로 이루어진 데이터의 집합. 순서는 유지되지 않으며, 키는 중복을 허용하지 않고, 값은 중복을 허용한다.

ArrayList, HashMap, Properties

Arraylist(단방향)
Iterator 패턴  : 안에 있는 데이터가 몇 개 인지 모르지만 모두 출력하고 싶을 때.
