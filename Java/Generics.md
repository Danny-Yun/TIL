# 제네릭스(Generics)
<br>

- 제네릭스는 다양한 타입의 객체들을 다루는 메서드나 컬렉션 클래스에 컴파일 시의 타입체크를 해주는 기능이다.    
- 객체의 타입을 컴파일 시에 체크하기 때문에 객체의 타입 안정성을 높이고 형 변환의 번거로움이 줄어드는 장점이 있다.    
그만큼 코드가 간결해진다. 
     
제네릭 생성은 생략하고, 사용하는 방법에 대해서만 정리해보자.

<br>

코드는 다음과 같다. 

```java
ArrayList<String> aList = new ArrayList<String>();
```

제네릭스는 자바 J2SE 5.0 이후에 도입된 개념이다.     
도입되기 전인 J2SE 1.4까지는 위의 코드를 다음과 같이 사용했다. 

```java
ArrayList aList = new ArrayList();
```

두 코드의 차이점은 ArrayList라는 자료형 타입 바로 옆에 `<String>`과 같은 문구가 있느냐 없느냐의 차이이다.     
위에서 사용한 첫번째 코드의 `<String>`이라는 제네릭스 표현식은 **"ArrayList 안에 담을 수 있는 자료형은 String 타입뿐이다"** 라는 것을 의미한다. 즉 제네릭스를 이용하면 좀 더 명확한 타입체크가 가능해지는 것. 

<br><br/>

```java
ArrayList aList = new ArrayList();
aList.add("hello");
aList.add("java");

String hello = (String) aList.get(0);
String java = (String) aList.get(1);
```

**위처럼 제네릭스를 사용하지 않을 경우** ArrayList 안에 추가되는 객체는 Object 자료형으로 인식된다.     
Object 자료형은 모든 객체가 상속하고 있는 가장 기본적인 자료형이다. 따라서 ArrayList 객체인 aList에 값을 넣을 땐 문제가 없다.     
하지만 값을 가져올 경우에는 항상 Object 자료형에서 String 자료형으로 다음과 같이 형 변환(casting)을 해주어야만 한다. 

<br>

그리고 aList 안에는 String 객체 이외의 객체도 넣을 수 있기 때문에 형 변환 과정에서 잘못된 형 변환으로 인한 오류가 발생할 소지가 있다. 바로 이러한 점이 제네릭스 탄생의 이유이기도 하다. 

<br><br/>

```java 
ArrayList<String> aList = new ArrayList<String>();
aList.add("hello");
aList.add("java");

String hello = aList.get(0);
String java = aList.get(1);
```
**위처럼 제네릭을 이용하면** 자료형에 대한 형 변환 과정이 필요없다. 이미 컴파일러가 aList에는 반드시 String 자료형만 추가되어야 함을 알기 때문이다. 형 변환에 의한 불필요한 코딩, 잘못된 형 변환으로 인한 런타임 오류등에서 벗어날 수 있게 된다. 

<br>
