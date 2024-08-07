# reading_dev_book, lecture
읽은 책 / 강의 간단하게 소회 남기기 2021~
----

2024
## 책
1. tyde first
   - 켄트백의 소프트웨어 설계에 대한 이야기 3부작 중 1부
   - 작은 코드정리부터 시작해서 변화와 수정에 대한 이야기를 한다. 구체적 이야기보다는 전반적인 작업의 태도와, 그것을 팀원들과 전파하는 것에 대한 이야기에 가깝다.
   - 소프트웨어 설계의 방법론이라기보다는 설계에 대한 자세와 대응을 정리한 책. 특정 아키텍쳐나 설계방법론에 대한 갈증을 해결해주진 않지만 오히려 항상 어떻게 해도 흐릿했던 소프트웨어 설계라는 행위에 대한 과정이 조금 더 밝아진 것 같다
2. OpenAPI와 스웨거를 활용한 실전 API 설계
   - API 사용자는 모든것을 할 수 있다. 제한된 동작을 정의하라
   - API 정보는 정확하고 풍부하게 전달되어야하며, 적절한 도구가 이러한 비용을 최소화 해줄 수 있다(OpenAPI 스펙 및 swaggerUI등)
   - API 테스트를 자동화 하는 것은 필수적이다.
   - RESTful API 와 같은 API 디자인 규약을 잘 준수하는것이 API 사용자에게 더 좋은 사용자 경험을 제공한다
   - API 사용자는 작은 변경이나 장애, 스트레스에도 떠날 수 있다. 떠난 사용자를 되돌리는 것은 매우 어렵다
   - API 스키마는 스키마 간의 관계와 역할을 명확히 정의하는 것이 중요하다. 
   - 중대 변경에 대한 API 수정 => 중대 변경이 없는것이 가장 좋다 (object로 감싸기)
   - 버저닝 전략은 매우 중요하지만, API 사용자와 구체적인 협의가 필요하다는 점에서 주의가 필요하다
   - API 설계는 프론트엔드에서 먼저 하는것도 좋은 방법이다 (사용자가 원하는 것을 더 잘 알 수 있다)
   - 문서화와 일관성은 중요하다. 유일한 최신정보를 보장하라.
   - 인증, 인가, 방화벽 등을 통해 API를 항상 보호해야한다.
   - API 모니터링을 통해 항시 상태를 점검할 수 있도록 구성하라.
  3. 그림으로 보는 알고리즘
  4. 데이터 중심 어플리케이션 설계
     - 1장
         신뢰성
       - 오류의 최소화, 하드웨어/소프트웨어/인적오류
         유지보수성
       - 운용성: 모니터링, 자동화, 좋은 문서와 단순한 모델, 예측 가능한 동작, 관리자에 의한 시스템 제어 가능 상태
       - 단순성: 복잡도 관리, 좋은 추상화, 복잡한 문제가 아닌 복잡한 구현을 해소하기
       - 발전성: 변화를 쉽게 하기, 민첩하게 변경할 수 있도록 유지하는 것
        
     - 2장
       - 데이터 모델링 및 데이터 모델은 어플리케이션에서 계층적으로 활용된다
       - SQL진영의 정규화의 핵심은 쓰기 오버헤드와 불일치를 피하기 위해 데이터의 불필요한 중복을 제거하는 일이다.
       - 어플리케이션 조인으로 조인을 대신할 경우 메모리의 부하를 고려해야한다
       - 문서형 데이터 모델은 1:N 관계에서 관계형 모델보다 훨씬 수월하게 동작하지만, N:1 또는 M:N 관계에서는 데이터를 중복으로 지닐지, 참조로 해결할지에 대한 고민이 있다(주: mongodb에서는 이러한 데이터를 중복을 허용하는 embedding 방식을 사용하길 추천하지만, 데이터 수정의 오버헤드문제는 여전히 해결되지 않는 문제다)
       - 관계형 모델과 문서 데이터 모델은 모델 자체만으로 봤을 때, 스키마 유연성 및 지역성에 기인한 성능은 문서 데이터 모델이 우수하고, 조인, 다대일, 다대다 관계를 더 잘 지원하는 것은 관계형 모델이 적합하다.
       - 상호 연결이 많은 경우 관계형 모델이 어플리케이션 코드를 더 단순하게 만들어주며
       - 한 문서에 계층적으로 다 표현되는 데이터 모델이 필요하다면 문서형 모델이 어플리케이션 코드를 더 단순하게 만들어준다.
       - 애플리케이션은 데이터가 특정 구조를 갖는다고 가정할 가능성이 높다. 스키마가 명시적인지(쓰기에 강요됨),암시적인지 (읽기에 다뤄짐)의 문제일 뿐이다

     - 3장
       - 트리 분석
       - 데이터 저장소의 특징(디스크와 인메모리)
       - 색인 -> 디스크의 한계를 넘어서기위한 기법들의 발전
       - OLTP 질의 유형 -> 통계, 분석 등 일반적인 트랜잭션 이아님
       - 데이터 웨어하우징 -> OLTP를 위한 별도의 데이터 웨어하우스 적재
       - 데이터웨어하우스에서의 스키마 유형 -> 눈꽃송이 스키마
       - 개별 트랜잭션 이벤트를 저장하고, 트랜잭션에 엮인 다른 데이터 테이블들의 pk를 참조로 갖고있으므로서 테이블 주변이 눈꽃송이처럼 보인다는 뜻. (좀 더 심도있게 이해할 필요있음)
       - 집계/통계를 위한 데이터 구조의 특징 -필요한 데이터 조회수를 줄이기 위한 기법을 활용해 스토어를 구축한 데이터베이스(카산드라같은)
       - 수백만건 이하에서 고려할 케이스는 아닐 수 있음
       - 데이터를 비트맵 압축해서 더 효율적으로 만들수도있음(유니크한 정보들에 대해)

     - 4장
       - 다양한 부호화를 통해 네트워크 전송 시 바이트를 줄일 수 있다
       - 프로그래밍 언어 종속적으로 특화된 부호화는 호환성을 제공하지 못하는 경우가 있어 주의해야한다.
       - JSON, XML이 가장 대중적으로 쓰이지만, 프로토콜버퍼와 같은 부호화 된 데이터 전송 형식도 인기를 얻고있다
       - 웹서비스 에서는 REST, SOAP 과 같은 방식의 전송형태가 대중적으로 이용되고있다
       - RPC의 경우 유용함과 동시에 주의할 점이 몇 가지 있다
            1. 로컬함수에 비해 타임아웃 위험성이 있는데, 이 경우 제대로 처리가 됐는지 알기가 어렵다
            2. 실패한 네트워크 요청을 재시도하면, 이미 처리된 문제를 또 처리하게 되는 경우도 있다. 응답만 유실되는 경우가 있기 때문. 따라서 멱등성을 보장하기 위한 다른 기법이 필요할 수 있다.
            3. 네트워크 함수 요청은 로컬 함수와 달리 응답시간에 대한 변수가 훨씬 많다
            4. 로컬함수는 포인터를 로컬메모리의 객체에 효율적으로 전달할 수 있지만, 네트워크로는 바이트로 부호화 하여 전송해야한다. 숫자나 문자열같은 원시데이터면 보통 문제가 없지만 큰 객체일 경우라면 문제가 될 수 있다.
            5. 클라이언트와 서비스는 다른 프로그래밍 언어로 구현될 수 있어서, RPC 프레임워크는 언어간 데이터타입 변환을 할 수 있어야 한다. 모두가 같은 타입을 갖는것은 아니다. 예를 들어 자바스크립트의 부동소수점문제(2의 53승 이상인 수)는 추가적인 변환을 통해 전송해야지만 제대로 된 처리가 가능하다. 단일 프로세스에서는 변형에 대한 고민이 줄어든다.
        - REST 는 공개된 API의 거의 표준처럼 쓰이며, RPC는 외부의 요청보다는 데이터센터 내의 같은 조직이 소유한 서비스 간 요청에서 더 주로 쓰인다.
        - API 버전 관리자는 호환성을 고려해야한다. 요청은 하위호환성이 필요하고, 응답은 상위 호환성이 필요하다. 여기서 하위호환성이란 새로운 코드, 내지는 데이터가 예전의 것과 호환되어야 한다는 것이고, 상위호환성이란 예전의 코드, 내지는 데이터가 새로운 것들과 호환되어야 한다는 것이다. 서비스제공자는 클라이언트를 제어할 수 없기 때문에 무한정에 가까운 호환성이 유지되어야 하며, 호환성을 깨는 변경에 대해서는 여러 API를 유지하는 것으로 대응한다.
        - 메세지브로커를 사용하는 방식은 비동기 메세지 전달 시스템이라고 부르며, 직접 RPC를 호출하는 것에 비해 장점이 있다.
            1. 수신자가 사용불가능하거나 과부하 상태라면 브로커가 버퍼의 역할을 겸한다
            2. 메세지 재전송을 통해 유실을 방지할 수 있다
            3. 송신자가 수신자의 정보를 알 필요가 없다
            4. 하나의 메세지를 여러 수신자에게 보낼 수 있다
            5. 논리적으로 송신자와 수신자가 분리된다
            6. 응답을 기다리지 않는 비동기 처리가 가능하다
         
     - 5장 복제
        - 복제에서의 어려움은 복제된 데이터의 변경 처리에 있다. 쓰기 뒤 읽기 일관성을 달성하기 위한 방법들이 필요하다. 자신이 쓴 내용 읽기는 특정 규칙을 정해서 master(primary)에서 읽게 하는 것이다. 이보다 좀 더 느슨한 것은 단조 읽기로, 특정 리드 레플리카에서 특정 유저군이 읽게하는 것으로 유저의 고유키와 해시함수를 이용해서 리드 레플리카를 정해서 읽는것이다. 이는 쓰기 후 읽기 일관성은 달성할 수 없지만 데이터를 일관적으로 읽는 것을 보장할 수 있다.(복제시간 차이에 따른 시간역전현상 방지) 비슷하지만 약간 다른 것으로, 일관된 순서로 읽기 보장이 있다. 가령 어떤 시간순으로 이뤄지는 쓰기가 발생한 것에 대해, 두 쓰기의 읽기 복제 지연이 서로 다르면 읽기 순서가 쓰기 순서를 보장하지 않아 이상하게 보일 수 있다. 이는 파티셔닝된(샤딩된) 데이터베이스에서 자주 등장한다. 즉, 쓰기의 전역 순서가 지켜지지 않는 상황에서 발생하기 쉽다.
        - 복제 지연을 위한 해결책은 근본적으로는 트랜잭션에 의존하는 것이다. 어플리케이션에서 조절하는 것은 위험성이 있다. 그러나 분산시스템에서는 이 해결책을 적용하는데 한계가 있기 때문에 더 나은 대안으로 최종적 일관성을 대부분 지향한다. 
        - 다중리더복제는 마스터-마스터 혹은 액티브-액티브 복제를 의미한다. 상당히 큰 복잡도를 불러일으키기 때문에 아주 특정한 상황에서만 고려하는 것이 좋다.(다중 데이터 센터 운영)
        - 쓰기충돌문제를 해결하는것이 필수적이다. 다중 데이터센터간 마스터의 충돌도 그렇지만 디바이스간의 데이터 동기화문제도 있다(오프라인에서 저장되는 기기의 데이터와 서버의 데이터 간 충돌 문제)
        - 충돌 회피의 가장 간단하고 많이 쓰이는 전략은 충돌 회피로, 특정 레코드의 모든 쓰기가 동일한 마스터를 거치도록 하는 것이다. 이 경우 다른 마스터로 트래픽을 우회해야하거나 하는 상황에서는 충돌 회피가 실패할 위험이 있다.
        - 데이터베이스는 수렴 방식으로 충돌을 해소해야 한다. 최종 값이 어떤 것 하나로 수렴해야 한다는 뜻.  타임스탬프 기준이나 복제서버의 고유 ID와 같은 기준을 이용할 수 있지만 데이터 유실 위험이 있다. 값을 병합하는 기준을 만들거나 명시적 데이터 구조에 충돌을 기록해 모든 데이터를 보존하고 충돌 해소는 어플리케이션에 위임하여 보여주는 방식을 바꾸는 방법도 있다. 충돌 해소는 보통 전체 트랜잭션이 아니라 개별 로우나 문서 수준에서 적용된다. 따라서 원자적으로 여러 다른 쓰기를 수행하는 트랜잭션이라면 각 쓰기는 충돌 해소를 위해 여전히 별도로 간주된다. 다중마스터 복제시스템은 데이터베이스별로 충돌감지와 기준이 다르므로 문서를 읽고 철저하게 테스트 해야한다.
        - 다이나모 스타일의 디비에서는 쓰기 요청과 읽기 요청을 병렬로하고, 일정 숫자의 노드에서 (일반적으로 과반수이상)성공하면 성공한것으로 간주한다. 실패한 노드는 추후에 성공한 노드와 데이터를 동기화하는 방식으로 작동한다. 그러나 엣지케이스 중에서는 쓰기가 과반 이하에서 성공해서 실패할 경우 이 데이터들이 성공한 복제서버에서는 데이터를 롤백하지 않아 더티리드와 비슷한 데이터 읽기가 일어날 수 있다. 느슨한 정족수의 경우 일시적인 복제간 장애에 대해 더 나은 내결함성을 제공하는데, 이는 잠시 정족수가 아닌 노드에도 쓰기를 받아들이게 하고, 장애가 해소된 뒤 이를 복제함으로서 해결하는 방식이다. 그러나 이것은 지속성 관점에서 쓰기에 대해 장점이 있지만 쓰여진 데이터에 대한 읽기 보장은 더 어려워진다.
        - 손실데이터를 허용할 경우, ‘최종승리쓰기’식 충돌해소방법이 적합하다. 예를들어, 타임스탬프에서 가장 최신인 쓰기로 수렴시킬 경우 같은 쓰기요청 중 그 이전것들은 무시한다.
        - 두 가지 작업이 ‘동시에’수행됐는지 여부는 인과성과 관련이 있다. 가령 작업 B가 A의 쓰기에 의존할경우(같은 레코드를 대상으로 A가 쓰여진 뒤 B가 다시 쓴다면) 이는 작업A가 작업B에 의존한다. 그러나 이렇게 서로 다른 작업에 대한 정보가 없다면 동시작업이라고 볼 수 있다. 이 경우 가능성은 B가 A이전일 때, A가 B 이전일 때, A와 B가 동시일 때로 나눌 수 있는데, 이것을 파악하기 위한 알고리즘이 별도로 필요하다.
       * 단일 primary - 다중 복제가 많은 사례에서 일반적으로 좋은 모델로 보인다
       * 다중 primary 와 primary없는 복제 시스템을 활용해야 할 경우 꼭 필요한지를 면밀히 검토하고 쓰기 충돌과 읽기 복제에서 일어날 수 있는 낮은 일관성에 대해 대응할 수 있는 방법들이 필요하다.

----
2023
## 책
1. 러닝 타입스크립트
   - 번역은 좀 별로지만 예제가 좋아서 타입스크립트를 좀 더 익숙하게 쓸 수 있게 되었다
   - 그런데 막상 타입스크립트의 심화 요소에 대해 설명하자니 잘 안될때가 있다.. 어차피 계속 쓸 테니까 익숙해지면서 나아질거라 생각한다.

----   
2022
기록 안함.. 

----
2021
## 책
1. Node.js 교과서 2판 
- 자바스크립트를 통한 Node.js 환경의 Express.js 개발을 해왔었는데 좀 더 정리할 수 있는 기회였음
- 작성된 코드에 대한 유지보수는 코드 모양을 보며 직관적으로 기능 개발만 했었는데 이 책을 통해 좀 더 Node.js 개발을 정확하게 할 수 있게 된 것 같다.

2. JavaSrcipt Deep Dive, 코어 자바스크립트
- 모던 자바스크립트(ES6+)를 제대로 공부하기 위해 읽었다. 두께만큼의 만족도가 있었다.
- 한번 정리하고 읽은걸로 끝나는게 아니고 활용을 자주 안하는 부분은 두고두고 자주 찾아봐야 할 것 같다.
- ES6+ 스타일의 코딩은 아는것 만큼이나 익히는게 중요해서 반복숙달 되어야 한다.
- 최신 책이긴 하지만 ECMAScript 공식 문서에 신경써야 한다는걸 느꼈다.

3. Do it 클론코딩 영화 평점 웹 서비스
- 가볍게 react가 뭔지 써보고 싶었다. 그럭저럭 재밌었다.
- 뭘 배웠다는 느낌보단 angular와 react의 스타일 차이를 느껴본 정도

4. 데이터 베이스 첫걸음
- 첫걸음이지만 첫걸음같은 착한 설명으로 RDBMS와 SQL에 대해 적절한 기초를 배운 느낌이다
- No-SQL만 써오던 입장에서 단비같은 책이 되어주었다.

5. 쓰면서 익히는 알고리즘과 자료구조
- 유형별로 문제를 단계적으로 분석하고 풀어나가는 연습을 할 수 있었다
- 파이썬 코드를 JS 코드로 바꿔 공부하는 재미도 있었다.
- 이 책으로 자료구조와 알고리즘을 잘 알게 된다기보단.. 앞으로 연습하는 방법을 제시해 준 것 같다
- 주먹구구 식으로 코딩테스트 연습 하던 때에 비해 이 책 덕에 공부하기가 한 결 편안해졌다. 그렇다고 쉬워진건 아니고..

6. 리팩터링 2판
- 어렵다... 리팩터링 이론이 어렵다기보단 읽고 아하 오케이 하고 코드에 적용하려고하면...
- 코드의 악취를 느끼고 그걸 바꾸는 과정에서 기준을 쌓는건 결국 각자의 경험 같았다. 
- 좋은 방향은 있지만 완벽한 답안은 없다.
- 다 읽었다. 한 번 읽고 과제를 해본 걸로는 모자란 것 같다.
- 가을즈음 사이드 프로젝트를 하면서 실제 테스트코드 - 리팩터링 두 가지 과정을 좀 적용해서 익혀봐야겠다

7. Node.js 디자인 패턴 바이블(디자인패턴 3판)
- Node.js로 백엔드를 구현한다면 무조건.. 무조건 읽어야한다.
- 난이도는 쉽지 않다. 그치만 Node.js를 다룬다면 거를 게 없는 책.

8. 오브젝트
- 나는 객체지향 프로그래밍 자체를 몰랐다는 생각이 든다.
- 데이터 중심 설계가 옳은 방법인줄 알았는데 생각이 와장창!
- 리팩터링 2판과 같이 꾸준히 신경써야 하는 내용들이어서 읽고 지나쳐버리면 의미가 없을 것 같다.

9. Learning SQL
- RDBMS를 좀 더 체계적으로 공부하기 위해 읽고 있다
- 단계별로 내용이 잘 정리되어 있고 실습하기 좋아서 좋다.

## 강좌
1. 패스트캠퍼스 컴퓨터공학 완주반
- 8주만에 다 소화하긴 어려운 분량.. 그치만 OS랑 시스템 프로그래밍만 건져도 좋았던 것 같다.
- 백지상태에 가까운 CS 지식에 대해 최소한의 인덱스는 만든 느낌.. OS강좌가 제일 좋았다.

2. 패스트캠퍼스 The RED 4천만 MAU.. 
- 시스템 디자인, 아키텍쳐에 전혀 관심이 없었다면 좋았을 것 같은데.. 구체화된 사례보다는 거시적인 뷰를 보여준다.
- 분명 얻은게 있긴한데, 강의 결제할 때의 기대였던 코드레벨의 디테일한 강좌는 아니었다.

3. 패스트캠퍼스 The RED 현실세상의 TDD
- TDD가 대체 뭔지 감이 잘 안잡혔는데 정말 좋았다
- TDD는 배운다고 해서 적용할 수 있는게 아니고 결국 코드를 고민하는 과정을 체계화 한 방식이라는 생각이든다.
- 그런면에서 TDD를 한다는건 코드를 작성하고 리팩토링 하는 일을 자연스럽게 연습하면서 바람직한 코드베이스의 유지보수와 맞닿아있는 느낌이다.
- 실무 코드에 테스트 코드를 만들면서 적용해보니 리팩토링이아니라 리스트럭쳐링을 하고있더라. 

4. 인프런 따라하며 배우는 TDD 개발
- TDD를 좀 더 연습하기 위해서 수강했다
- 내용이 새로운건 없었고 테스트 코드를 어떤 단위로 짜는지 좀 더 디테일하게 느낄 수 있었다.

5. 노마드코더 Nest.js backend free course
- Nest.js는 늘 관심이 있었기 때문에 수강했다
- TS환경에서 체계적인 백엔드 프레임워크로 express에 비해 잘 짜여진 아키텍쳐가 좋았다
- 자유롭게 작은 서비스를 만든다면 express.js도 편하지만.. 규모와 협업을 고려해야한다면 확실히 Nest.js가 좋아보인다.

6. 인프런 Slack 클론코딩 with Nest.js + TypeORM
- TypeScript랑 Nest.js, TypeORM을 손에 익히기 위해 듣고있다

7. 인프런 탄탄한 백엔드 Nest.js 기초부터 심화까지
- 위와 같이 Nest.js에게 익숙해지기 위해 듣고 있다. 

8. 인프런 AWS 입문자를 위한 강의 / 중 상급자를 위한 강의
- 회사의 인프라를 클라우드로 마이그레이션 해야해서 듣고 있다
- 각 aws의 방대한 기능들을 살펴보며 작은 실습을 통해 머릿속에 인덱스를 만드는 과정으로 느껴진다.

9. 인프런 모든 개발자를 위한 HTTP 웹 기본 지식
- 인프라를 보다보니 네트워크를 보게되고, 네트워크를 보다보니 내가 HTTP도 잘 모른다는 생각이 들었다.
- 이참에 한번 기초를 잡자는 목적으로 듣게 되었다. HTTP 완벽 가이드 책이 좋다는데 두깨가 무서워서 이것부터..
