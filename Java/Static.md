# 정적 변수와 메서드(static)

<br>

## static 변수

```java
class Work {
    String myLanguage = "Flutter"; 
}

public class Sample {
    public static void main(String[] args) {
        Work w1 = new Work();
        Work w2 = new Work();
    }
}
```

Work 클래스는 업무를 나타내는 클래스다. 위와 같은 클래스를 만들고 객체를 생성하면 객체마다 객체변수 myLanguage을 저장하기 위한 메모리가 별도로 할당된다. 이렇게 항상 값이 변하지 않는 경우에 static을 사용하면 메모리의 이점을 얻을 수 있다.

<br>

아래는 변경된 예제이다.

```java
class Work {
    static String myLanguage = "Flutter"; 
}

public class Sample {
    public static void main(String[] args) {
        Work w1 = new Work();
        Work w2 = new Work();
    }
}
```

위와 같이 myLanguage 변수에 static 키워드를 붙이면 자바는 메모리 할당을 딱 한번만 하게 되어 메모리 사용에 이점이 있다. 

> 만약 Work 클래스의 myLanguage 값이 변경되지 않기를 바란다면 static 키워드 앞에 final이라는 키워드를 붙이면 된다. 

<br>

static을 사용하는 또 한가지 이유로 **공유** 개념을 들 수 있다. static 으로 설정하면 같은 곳의 메모리 주소만을 바라보기 때문에 static 변수의 값을 공유하게 되는 것이다.

명확한 이해를 위해 다음의 예시처럼 웹 사이트 방문시마다 조회수를 증가시키는 Counter 클래스가 있다고 해보자.

```java
class Counter  {
    int count = 0;
    Counter() {
        this.count++;
        System.out.println(this.count);
    }
}

public class Sample {
    public static void main(String[] args) {
        Counter c1 = new Counter();
        Counter c2 = new Counter();
    }
}
```

위 Counter 클래스를 실행하면 다음과 같은 결과값이 나온다.

```java
1
1
```

c1, c2 객체 생성시 생성자에서 객체변수인 count의 값이 1씩 증가하더라도, c1과 c2의 count는 서로 다른 메모리를 가리키고 있기 때문에 원하던 결과(카운트가 증가된 결과)가 나오지 않는다. 객체변수는 항상 독립적인 값을 갖기 때문에 당연한 결과다.

<br>

```java
class Counter  {
    static int count = 0;
    Counter() {
        count++;  // count는 더이상 객체변수가 아니므로 this를 제거하는 것이 좋다.
        System.out.println(count);  // this 제거
    }
}

public class Sample {
    public static void main(String[] args) {
        Counter c1 = new Counter();
        Counter c2 = new Counter();
    }
}
```

int count 변수 앞에 static 키워드를 붙이면, count 값이 공유되어 다음과 같이 count가 증가되어 출력된다.

```java
1
2
```

보통 변수의 static 키워드는 프로그래밍시 메모리의 효율보다는 공유의 목적으로 훨씬 더 많이 사용하기도 한다.

<br>

## static 메서드

```java
class Counter  {
    static int count = 0;
    Counter() {
        count++;
        System.out.println(count);
    }

    public static int getCount() {
        return count;
    }
}

public class Sample {
    public static void main(String[] args) {
        Counter c1 = new Counter();
        Counter c2 = new Counter();

        System.out.println(Counter.getCount());  // static 메서드는 클래스를 이용하여 호출할 수 있다. 
    }
}
```

Counter 클래스에 `getCount()` 라는 static 메소드가 추가되었다. 메소드 앞에 static 키워드를 붙이면 `Counter.getCount()` 와 같이 객체 생성없이 클래스를 통해 메서드를 직접 호출할 수 있다.

> 스태틱 메소드 안에서는 객체변수 접근이 불가능 하다. 위 예시에선 count 변수가 static 변수이기 때문에 스태틱 메소드(static method)에서 접근이 가능하다.

보통 스태틱 메소드는 유틸리티성 메소드를 작성할 때 많이 사용된다. 예를 들어 "오늘의 날짜 구하기", "숫자에 콤마 추가하기" 등의 메소드를 작성할 때에는 클래스 메소드를 사용하는 것이 유리하다.


