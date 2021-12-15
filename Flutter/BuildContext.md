# 빌드컨텍스트(BuildContext)

## 정의

"A handle to the location of a widget in the widget tree."    

-> widget tree에서 현재 widget의 위치를 알 수 있는 정보

<br>

<img width="491" alt="빌드컨텍스트1" src="https://user-images.githubusercontent.com/86466976/146136049-92486bf1-6cb8-4ca4-97f0-59a917b771bb.png">

<br>

위 사진은 build 함수는 Scaffold 위젯을 리턴하는데, 이때 위젯트리 상에서 어디에 위치하는가에 대한 정보를 가지고 있는 context 라는 것을 넣어서 리턴을 해준다는 의미이다. 

<br>

"Each widget has its own BuildContext, **which becomes the parent of the widget returned by the StatelessWidget.build or State.build function.**"

-> 모든 위젯은 자신만의 BuildContext를 가지고 있다. **이 BuildContext는 stateless 위젯이나 state 빌드 메서드에 의해서 리턴된 위젯의 부모가 된다.**"
s

<br>

## 자주 볼 수 있는 오류

```dart
"Scaffold.of() called with a context that does not contain a Scaffold"
```

현재 Scaffold 위젯이 위젯트리상에서 어디에 위치하는지 알기 위해서, context를 참조하는 것이 당연한 것인데, 어디에 위치하는지에 대한 정보를 전혀 가지고 있지 못할 때 발생한다. 
