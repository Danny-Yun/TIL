# 생성자(Constructor)

이해를 돕기 위해 몇 가지 클래스를 먼저 작성해 보겠다. 

<br>

<i>Animal.java</i>
```java
public class Animal {
    String name;

    public void setName(String name) {
        this.name = name;
    }
}
```
<i>Dog.java</i>
```java
public class Dog extends Animal {
    
    public void sleep(int hour) {
        System.out.println(this.name+" zzz in house for " + hour + " hours");
    } 
}
```

<br>

```java
 public static void main(String[] args) {
        Dog dog = new Dog();
        System.out.println(dog.name);
}
```

위와 같이 작성하면, name 객체 변수에 아무런 값도 넣지않았기에 null이 출력될 것이다.    
만약 여기서 **생성자(Constructor)** 를 사용하면, 변수에 값을 무조건 입력해야만 객체가 생성될 수 있도록 강제할 수 있다. 

<br>

클래스에 다음과 같은 메서드를 추가해보자.
```java
public Dog(String name) {
    this.setName(name);
} 
```
위 메서드처럼 메서드명이 클래스명과 동일하고 리턴 자료형이 없는 메소드를 생성자(Constructor)라고 말한다.

<br>

***생성자의 규칙***
1. 클래스명과 메소드명이 동일하다.
2. 리턴타입을 정의하지 않는다.

<br>

생성자는 다음과 같이 new 라는 키워드로 객체가 만들어질 때 호출된다.    
생성자는 메서드와 마찬가지로 입력을 받을 수 있다.
```java
new 클래스명(입력항목, ...)
```

<br> 

위의 예시로 돌아가서, 생성자를 만들고 객체 선언시에 입력값을 넣어주면
```java
public class Dog extends Animal {
    
    public HouseDog(String name) {
        this.setName(name);
    } 

    public void sleep(int hour) {
        System.out.println(this.name+" zzz in house for " + hour + " hours");
    } 

     public static void main(String[] args) {
        Dog dog = new Dog("Choco");
        System.out.println(dog.name);
    }
}
```
아래처럼 main메서드 실행시 이제 null값이 뜨지 않고, 결과가 출력되는 것을 확인할 수 있다.   
```java
Choco
```

이처럼 생성자를 사용했을 때 얻게 되는 이점은 `setName("Choco")`와 같은 필수적인 행동을 객체 생성할 때 제어할 수 있게 된다는 점이다. 