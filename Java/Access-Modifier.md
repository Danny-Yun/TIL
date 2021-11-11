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