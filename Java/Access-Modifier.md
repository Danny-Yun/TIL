# 접근제어자 (Access Modifier)

자바에는 다음과 같은 접근 제어자들이 있다. 

1. public
2. protected
3. default
4. private

**public > protected > default > private** 순으로 보다 많은 접근을 허용한다. 

<br>

## private

```java
public class AccessModifier {
    private String secret;
    private String getSecret() {
        return this.secret;
    }
}
```
접근제어자가 private으로 설정되었다면 private이 붙은 변수, 메서드는 해당 클래스에서만 접근이 가능하다. 
위의 secret 변수와 getSecret 메서드는 오직 AccessModifier 클래스에서만 접근이 가능하고 다른 클래스에서는 접근이 불가능하다.

<br>

## default
*StarPlayer.java*
```java
package team.chelsea;

public class StarPlayer {
    String lastname = "kante";
}
```
*Manager.java*
```java
package team.chelsea;

public class Manager {
    String lastname = "tuchel";

    public static void main(String[] args) {
        StarPlayer starPlayer = new StarPlayer();
        System.out.println(starPlayer.lastname);
    }
}
```
접근제어자를 별도로 설정하지 않는다면 접근제어자가 없는 변수, 메서드는 default 접근제어자가 되어 해당 패키지 내에서만 접근이 가능하다.
위의 StarPlayer와 Manager의 패키지는 team.chelsea로 동일하다. 따라서, Manager 클래스의 main 메서드에서 사용한 것과 같이 starPlayer.lastname으로 StarPlayer의 lastname변수로 접근이 가능하다.

<br>

## private
*Manager.java*
```java
package team.chelsea;

public class Manager {
    protected String lastname = "tuchel";
}
```
