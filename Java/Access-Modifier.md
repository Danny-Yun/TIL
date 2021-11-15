# 접근제어자 (Access Modifier)

자바에는 다음과 같은 접근 제어자들이 있다. 

1. public
2. protected
3. default
4. private

**public > protected > default > private** 순으로 보다 많은 접근을 허용한다. 

<br>

## private
접근제어자가 private으로 설정되었다면 private이 붙은 변수, 메서드는 해당 클래스에서만 접근이 가능하다. 
```java
public class AccessModifier {
    private String secret;
    private String getSecret() {
        return this.secret;
    }
}
```
위 예시의 cret 변수와 getSecret 메서드는 오직 AccessModifier 클래스에서만 접근이 가능하고 다른 클래스에서는 접근이 불가능하다.

<br>


## default
접근제어자를 별도로 설정하지 않는다면 접근제어자가 없는 변수, 메서드는 default 접근제어자가 되어 해당 패키지 내에서만 접근이 가능하다.

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
위 예시의 StarPlayer와 Manager의 패키지는 team.chelsea로 동일하다. 따라서, Manager 클래스의 main 메서드에서 사용한 것과 같이 starPlayer.lastname으로 StarPlayer의 lastname변수로 접근이 가능하다.

<br>


## protected
접근제어자가 protected로 설정되었다면 protected가 붙은 변수, 메서드는 동일 패키지내의 클래스 또는 해당 클래스를 상속받은 외부 패키지의 클래스에서 접근이 가능하다.

*StarPlayer.java*
```java
package team.chelsea;

public class StarPlayer {
    protected String lastname = "kante";
}
```
*NGoloKante.java*
```java
package team.chelsea.fullname;

public class NGoloKante extends StarPlayer {
    public static void main(String[] args) {
        NGoloKante ngk = new NGoloKante();
        System.out.println(ngk.lastname);       
    }   
}
```
위 예시의 StarPlayer클래스를 상속받은 NGoloKante이라는 클래스의 패키지는 team.chelsea.fullname으로,     
StarPlayer의 패키지인 team.chelsea와 다르지만, StarPlayer의 lastname 변수가 protected로 설정되었기 때문에     
ngk.lastname과 같은 접근이 가능하다.      
<br>
만약 lastname의 접근제어자가 protected 가 아닌 default 접근제어자였다면 ngk.lastname 문장은 컴파일 에러를 유발하게 된다.

<br>


## public
접근제어자가 public으로 설정되었다면 public 접근제어자가 붙은 변수, 메서드는 어떤 클래스에서라도 접근이 가능하다.
```java
package team.chelsea;

public class StarPlayer {
    protected String lastname = "kante";
    public String info = "He is No.7";
}
```
위 예시의 StarPlayer의 info 변수는 public 접근제어자가 붙어 있으므로 어떤 클래스에서던지 접근이 가능하다.

<br>

접근제어자를 모두 public으로 설정해도 프로그램은 잘 동작할 것이다. 하지만 접근제어자를 이용하면 프로그래머의 코딩 실수를 방지할 수 있고, 기타 위험요소를 제거할 수 있는 등의 많은 장점이 있다.
