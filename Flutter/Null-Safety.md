# 널 세이프티 이슈(Null Safety)

- Null : 아직 값이 정해지지 않은 것

<br>

1. 모든 변수는 null이 될 수 없으며, non-nullable 변수에는 null 값을 할당할 수 없다.
```dart
void main() {
    // 바로 컴파일 에러가 뜸
    String name;
    int age = null;
}
```

2. non-nullable 변수를 위한 null check가 필요 없다. 

3. "**Class 내의 변수는**" 반드시 선언과 동시에 초기화를 시켜야 한다. 
```dart
class Person {
    // 아래와 같이 초기화
    int age = 21;
}
```

<br>

## 변수에 null 값이 필요한 경우에 대처하는 방식

- **?** - Nullable type
```dart
class Person {
    String? name;
}
```

<br>

- **late**
```dart
class Person {
    late int age;

    void setAge(int num) {
        age = num;
    }
}

void main() {
    final alex = Person();
    alex.setAge(22);
    print(alex.age);
}
```

<br>

- **!** - Not nullable type(null이 오지 않을 거라는 확신이 있을 때)
```dart
void main() {
    int x = 50;
    int? y;
    if (x > 0) {
        y = x;
    }
    
    int value = y!;
    print(value);
}
```

<br>

- **required** - not optional
```dart
int add({required int a, required int b}) {
    int sum = a + b;
    return sum;
}

void main() {
    print(add());
}
```






