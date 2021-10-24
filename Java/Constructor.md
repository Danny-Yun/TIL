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