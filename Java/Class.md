# 클래스(Class)

<br>

## 객체(Object)

아래의 Animal 클래스는 가장 간단한 형태의 클래스이다. 이 껍데기뿐인 클래스도 아주 중요한 기능을 가지고 있다.   
그 기능은 바로 **객체(object)를 만드는 기능**이다.
```java
public class Animal {

}
```

<br>

객체는 다음과 같이 만들 수 있다. 
```java
Animal cat = new Animal();
```
`new`는 객체를 생성할 때 사용하는 키워드이다.   
이렇게 하면 Animal 클래스의 인스턴스(instance)인 cat, 즉 Animal의 객체가 만들어진다. 

<br>

+ 과자틀 - 클래스(class)
+ 과자틀에 의해 만들어진 과자들 - 객체(object)

<br>

다음과 같이 무수히 많은 동물 객체들을 Animal 클래스로 만들 수 있다. 
```java
Animal cat = new Animal();
Animal dog = new Animal();
Animal horse = new Animal();
Animal pig = new Animal();
...
```

<br>

## 객체 변수 (Instance Variable)
Animal 이라는 껍데기 클래스를 조금 더 발전시켜 보자.   
Animal 클래스에 의해 만들어지는 동물들에 이름을 지을 수 있도록 해보겠다.
```java
public class Animal {
    String name;
}
```
이렇게 클래스에 선언된 변수를 **객체 변수**라 부른다.   
또는 인스턴스 변수, 멤버 변수, 속성이라고 말하기도 한다.

<br>

<span style="color:brown">클래스에 의해 생성되는 것은 객체, 그리고 그 클래스에 선언된 변수는 객체 변수(멤버 변수)라고 보면 된다.</span>

<br>

## 메서드
클래스에는 객체 변수와 더불어 **메서드**라는 것이 있다.   
객체 변수에 값을 대입하는 방법에는 여러가지가 있을 수 있지만 여기서는 가장 보편적인 방법인 메서드를 활용해보겠다.    
```java
public class Animal {
    String name;

    public void setName(String name) {
        this.name = name;
    }

    public static void main(String[] args) {
        Animal cat = new Animal();  // 객체 생성
        cat.setName("tom");  // 메서드 호출
        System.out.println(cat.name);
    }
}
```
Animal클래스에 추가된 setName메서드는 다음과 같은 형태의 메소드이다.
+ 입력 : String name
+ 출력 : void(리턴X)

<br>

```java
cat.setName("tom");
```
객체 변수에 접근하기 위해서 `객체.변수`와 같이 도트연산자(.)로 접근할 수 있었던 것처럼, `객체.메서드`로 객체가 메서드를 호출할 수 있다. 

<br>

```java
this.name = name;
```
여기서 `this`는 Animal 클래스에 의해서 생성된 객체를 지칭한다.    
만약 `Animal dog = new Animal()`와 같이 dog객체를 만들고,    
`dog.setName("happy")`와 같이 dog객체에 의해 setName 메서드를 호출하면     
setName 메소드 내부에 선언된 this는 바로 dog 객체를 지칭하게 된다.

