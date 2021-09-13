# 객체(Object)

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
