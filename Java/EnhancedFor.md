# 향상된 for문

```java
for(자료형 변수명 : 배열명) {
	문장
}
```
향상된 for문은 반복문 진행시 타겟으로 배열을 넣는다.     
이 경우 반목 실행 횟수는 배열의 내부요소 개수만큼 돌아간다.

<br>

```java
    int[] arr = {100, 200, 300, 400, 500};
    
    for(int i : arr) {
        System.out.println(i);
    }
```
위 코드의 출력 결과는 다음과 같다. 
```java
100
200
300
400
500
```