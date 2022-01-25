# 빌드컨텍스트(BuildContext)

## 정의

"A handle to the location of a widget in the widget tree."    

-> widget tree에서 현재 widget의 위치를 알 수 있는 정보

<br>

**BuildContext**는 앱을 만들 때 알아야 할 중요한 개념 중 하나로 전체 위젯 트리를 추적하는 것과 관련이 있으며특히 트리에서 위젯의 위치와 관련이 있다. 카운터 앱의 색을 바꿨던 것처럼 ThemeData에서 테마를 갱신하면 위젯 트리의 모든 자식 위젯을 갱신한다. 

위젯의 모든 build 메서드는 위젯 트리에서 위젯의 위치를 참조하는 BuildContext 하나를 인수로 받는다. build는 프레임워크가 호출하므로 BuildContext를 개발자가 관리할 필요는 없지만 이를 자주 사용하게 된다. 

<br>

빌드 컨텍스트는 특정 위젯을 정확하게 어떻게 표현할지 결정한다. 

빌드 컨텍스트는 위젯 자체의 정보가 아니라 위젯 트리에서 위젯의 위치 정보를 포함한다.

<br>

<img width="491" alt="빌드컨텍스트1" src="https://user-images.githubusercontent.com/86466976/146136049-92486bf1-6cb8-4ca4-97f0-59a917b771bb.png">

<br>

위 사진은 build 함수는 Scaffold 위젯을 리턴하는데, 이때 위젯트리 상에서 어디에 위치하는가에 대한 정보를 가지고 있는 context 라는 것을 넣어서 리턴을 해준다는 의미이다. 

<br>

"Each widget has its own BuildContext, **which becomes the parent of the widget returned by the StatelessWidget.build or State.build function.**"

-> 모든 위젯은 자신만의 BuildContext를 가지고 있다. **이 BuildContext는 stateless 위젯이나 state 빌드 메서드에 의해서 리턴된 위젯의 부모가 된다.**"


<br>

## 자주 볼 수 있는 오류

```dart
"Scaffold.of() called with a context that does not contain a Scaffold"
```

현재 Scaffold 위젯이 위젯트리상에서 어디에 위치하는지 알기 위해서, context를 참조하는 것이 당연한 것인데, 어디에 위치하는지에 대한 정보를 전혀 가지고 있지 못할 때 발생한다. 
