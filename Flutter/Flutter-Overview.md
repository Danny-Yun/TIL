# 플러터 개요(Overview)
<br>

플러터는 구글에서 만들어 오픈소스로 공개한 모바일 SDK이다. 누구나 아름다운 모바일 앱을 만들 수 있도록 하는 것이 플러터의 좌우명이다. 

플러터는 앱 개발에 완벽한 SDK다. 플러터는 렌더링 엔진, UI 컴포넌트, 테스트 프레임워크, 도구, 라우터 등 앱을 만드는 데 필요한 모든 기능을 제공하는 플랫폼이다. 덕분에 개발자는 앱 구현에 집중할 수 있다. 다른 부분은 플러터가 알아서 처리하므로 특히 앱 특유의 도메인 기능에 집중할 수 있다. 플러터의 가치는 놀라울 정도다.  

거시적인 관점에서 모바일 앱 개발은 새로운 분야이다. 이는 개발자와 회사 모두에게 큰 불편함이었다. 하지만 플러터가 등장하면서 양상이 완전히 바뀌었다.

<br>

- 플러터는 상속보다 조합을 중시한다. 조합은 ‘갖고 있는(has a)’ 관계를, 상속은 ‘~이다(is a)’ 관계를 정의한다.
- 위젯은 대부분 const 생성자를 갖는다. 플러터에서 위젯을 만들 때 new와 const 키워드는 생략하는 것이 좋다.
- StatefulWidget은 상태 객체로 자신의 내부 상태를 관리한다. StatelessWidget은 ‘뇌가 없으며’ 플러터가 위젯 트리에서 위젯을 제거하면 완전히 파괴된다.
- initState와 기타 생명주기 메서드는 상태 객체의 강력한 도구다.
- BuildContext는 위젯 트리에서 위젯의 위치를 가리킨다. 즉 위젯은 트리에서 자신의 위치 정보를 얻을 수 있다.
- 요소 트리는 영리하다. 요소 트리는 위젯을 관리하며 실제 사용될 요소의 청사진 역할을 한다.
- 플러터에서는 위젯과 관련된 RenderBox 객체가 위젯을 그린다. 이들 RenderBox는 위젯의 실제 물리적 크기를 결정한다. 이들 객체는 부모로부터 제약 조건을 받아 자신의 실제 크기를 결정한다.
- Container 위젯은 개별 위젯에서 얻어야 할 정보를 ‘편리하게’ 모아 제공한다.
- 플러터의 Row, Column 위젯은 CSS의 FlexBox와 비슷한 플렉스 레이아웃 개념을 사용한다.

<br><br/>

### 플러터 프로젝트 구조

<br>

pubspec.yaml → 모든 다트 프로젝트에 필요하며 의존성과 메타데이터를 관리한다.  

pubspec.lock → 편집하면 안 되는 잠금(lock)파일을 생성한다. pubspec.yaml을 업데이트할 때 이 잠금 파일을 갱신하며 호환되지 않는 패키지 버전을 사용하지 않도록 확인한다.

<br>

핵심은 모든 UI가 위젯이라는 것이다. 심지어 앱의 경로도 위젯이며 별도의 객체나 클래스가 따로 존재하지 않는다. App이라는 특별한 객체는 없다. build메서드로 다른 위젯을 반환하는 MyApp이라는 커스텀 위젯을 정의한다.

<br>

모든 위젯은 다른 위젯을 반환하는 build 메서드를 반드시 포함해야 한다.

<br>

**핫 리로드**는 네이티브 모바일 개발자에게 가장 군침이 도는 플러터 기능 중 하나다. 이 기능에 흥분하지 않는 사람이 있으리라 상상하기 어렵다. 

다트는 AOT 컴파일러이면서 JIT 컴파일러다. 컴퓨터로 앱을 개발할 때는 JIT을 사용한다. 실시간으로 코드를 컴파일하고 실행한다는 의미에서 ‘just in time’ 컴파일러라 부른다. 앱을 제품으로 배포할 때는 AOT 컴파일러를 사용한다. 

개발자 입장에서 개발 시에는 코드를 빨리 개발하고 재컴파일할 수 있으며, 제품 배포 시에도 네이티브 성능을 희생하지 않아도 된다.