# 맵(Map)

맵은 사전(dictionary)과 비슷하다. people이란 "사람", baseball이라는 단어는 "야구"라는 뜻이 부합되듯이 Map은 Key와 Value라는 것을 한 쌍으로 갖는 자료형이다. 

<br>

만약 사람을 예로 들면 누구든지 "이름" = "김자바", "생일" = "몇 월 몇 일" 등으로 구분할 수 있다. 자바의 맵은 이러한 대응관계를 쉽게 표현할 수 있게 해 주는 자료형이다. 


| Key | Value |
|:------:|:------------:|
| People | 사람 |
| Baseball | 야구 |


| Key | Value |
|:------:|:------------:|
| 이름 | 김자바 |
| 생일 | 5월 14일 |
| ... | ... |

<br>

## 특징
맵(Map)은 리스트나 배열처럼 순차적으로 해당 요소 값을 구하지 않고 key값을 통해 value값을 얻는다. 만약, people이라는 단어의 뜻을 찾기 위해서 사전의 내용을 순차적으로 모두 검색하는 것이 아니라 people이라는 단어가 있는 곳만 펼쳐보는 것이다. 

<br>

자바의 맵 중 가장 간단한 HashMap에 대해 알아보자.

<br/>

## .put
```java
HashMap<String, String> map = new HashMap<String, String>();
map.put("people", "사람");
map.put("baseball", "야구");
```
key와 value는 위에서 보듯이 put메소드를 이용하여 입력할 수 있다. 
> HashMap 역시 제네릭스를 이용한다. 위의 HashMap의 제네릭스는 모두 String 타입

<br>

## .get
```java
System.out.println(map.get("people"));
```
위처럼 key에 해당하는 value값을 얻기 위해서 get 메서드를 이용하면 value값을 얻을 수 있다. 

<br>

## .containsKey
```java
System.out.println(map.containsKey("people"));
```
containsKey 메서드는 맵에 해당 key값이 존재하는지 조사하여 결과값을 리턴한다. 
위 예제는 "people"이라는 키는 존재하므로 true가 출력될 것이다. 



## .remove
```java
System.out.println(map.remove("people"));
```
remove 메서드는 key값에 해당하는 아이템(key, value)을 삭제한 후 그 value값을 리턴한다.      
위 예제에선 "people"에 해당하는 아이템(people:사람)이 삭제된 후 "사람"이 출력된다. 

<br>

## .size
```java
System.out.println(map.size());
```
size 메서드는 Map의 갯수를 리턴한다. "people", "baseball" 두 값을 가지고 있다가 "people" 항목이 삭제되었으므로 1이 출력될 것이다.
