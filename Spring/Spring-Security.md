# 스프링 시큐리티 

<br>

| 표현식 | 역할 |
|:------:|:------------:|
| hasRole([role]) <br> hasAuthority([authority]) | 로그인한 사용자가 제시한 권한이 있으면 true, 없으면 false |
| hasAnyRole([role, role2]) <br> hasAnyAuthority([authority]) | 제시된 권한 중 하나만 가지고 있어도 true, 하나도 없으면 false |
| principal | 현재 접속 사용자의 전체적인 정보 |
| permitAll | 모든 사용자에게 허용 |
| denyAll | 모든 사용자에게 거부 |
| isAnonymous() | 익명 사용자이면 true(로그인 안한 사용자도 익명으로 간주) |
| isAuthenticated() | 인증된 사용자이면 true |
| isFullyAuthenticated() | 자동로그인으로 접속하지 않은 사용자이면서 권한이 맞으면 true |
