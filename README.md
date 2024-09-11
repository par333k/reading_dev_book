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
     
     - 6장 파티셔닝(샤딩)
       - 파티셔닝의 목적은 데이터와 질의 부하를 노드 사이에 고르게 분산시키는 것. 쏠림이 있으면 파티셔닝의 효과는 떨어진다. 키 범위 기준 파티셔닝은 어떤 키가 어느 파티션에 있는지 알기 쉬운 반면 특정한 접근 패턴이 핫스팟을 유발하는 단점이 있다.
       - 키의 해시값 기준 파티셔닝은 해시함수를 통해 데이터를 균일하게 분산시킨다. 암호적으로 해시함수가 강력할 필요는 없다.  파티션 경계는 크기가 동일하도록 나눌 수도 있고 무작위에 가깝게 선택할 수도 있다 (무작위 선택-일관성 해싱은 실제로는 잘 작동하지 않아서 잘 안쓰인다고 한다.) 해시값 기준 파티셔닝은 범위 질의를 효율적으로 실행하기 어려운 문제가 있다. 쏠린 작업부하와 핫스팟 완화를 위해서는 쏠린 키에 임의의 숫자 등을 붙이거나 해서 파티셔닝을 하는 방법이 있지만 이 경우도 읽기를 실행할 때 이 부분을 고려해야하는 문제가 있어 소수의 키에만 적용하는게 좋다.
       - 파티셔닝 기준 색인 설정에 대해 전역(용어 파티셔닝)색인은 읽기가 효율적인 반면 쓰기에서 단점이 있다. 문서 기준 색인은 지역색인이라 불리며 쓰기에서 효율적이지만 특정 파티션에 해당 색인에 포함되는 데이터가 있다는 보장이 없어 탐색이 늘어날 수 있다.
       - 전역 보조 색인은 대개 비동기로 갱신되기 때문에 쓰기 실행 후 바로 색인에 데이터가 반영되지 않을 수도 있다.
       - 파티션 전략 또는 파티션 재균형화 전략에서는 해시값에 모듈러 연산을 쓰지 않는게 좋다. 재균형 시 키가 자주 이동해 비용이 지나치게 커질 수 있다.
       - 재균형화 방법중에는 전체 파티션 개수를 고정하고 한 노드에 여러 파티션을 유지해 추가되는 노드에 파티션을 통째로 이전하는 방식이 있다. 이런 방식은 최초에 파티션 개수를 정하면 거의 고정이 되므로 확장을 위해 충분히 많은 숫자를 미리 준비하는게 좋지만, 그만큼 관리 오버헤드와 비용을 고려해야한다.
       - 고정 파티셔닝과 다르게 동적 파티셔닝이 있다. 키 범위 파티셔닝을 쓰는 데이터베이스는 파티션을 동적으로 만든다. 동적 파티셔닝은 기준 용량에 도달하면 이를 절반으로 쪼개는 식으로, B트리의 최상위 레벨에서 실행되는 작업과 유사하다. 이는 전체 데이터 용량에 맞춰 파티셔닝이 되므로 효율적이지만, 맨 처음에는 시작할 때 파티션이 하나이다. 몽고 디비와 같은 것에서는 사전 분할 방식으로 초기에 파티션 집합을 설정하게 하기도 한다.
       - 노드 비례 파티셔닝은 카산드라에서 사용하는 것으로, 파티션 개수가 노드 대수에 비례하게 하는 것이다. 즉, 노드당 할당되는 파티션 개수를 고정한다. 이 경우 노드 수 변화에 따른 유연한 확장성을 제공하지만, 파티션 수 변화로 인한 관리 복잡도가 증가할 수 있다. 파티션 경계를 무작위로 선택하기 위해 해시기반 파티셔닝을 사용한다.
       - 파티셔닝을 효과적으로 쓰기 위해 위 방법들을 조합하여 쓰기도 한다. 그러나 항상 파티셔닝의 관리 포인트가 늘어나는 점과 장애 관리의 자동화가 까다로워 질 수 있는 점을 잘 고려해서 결정해야 한다.

     - 7장 트랜잭션 (단일 장비 기준)
       - 트랜잭션은 어떤 어플리케이션이 어떤 동시성 문제와 어떤 종류의 하드웨어와 서프트웨어 결함이 존재하지 않는 것처럼 동작할 수 있게 해주는 추상층이다.
       - 트랜잭션은 요청-응답 전체를 이야기 할 수도 있고, 데이터베이스의 작업의 묶음일 수도 있다.
       - ACID와 BASE 같은 용어로 흔히 표현되지만, 아주 정확한 의미를 담는 것은 아니다.
       - 동시성 제어를 위한 격리 조건의 차이를 잘 알고 활용하는 것이 중요하다.
       - 경쟁 조건의 다양한 예시
           - 더티 리드: 한 클라이언트가 다른 클라이언트가 썼지만 아직 커밋되지 않은 데이터를 읽는다. 커밋 후 읽기 이상의 격리레벨로 방지가 가능하다
           - 더티 쓰기: 한 클라이언트가 다른 클라이언트가 썼지만 아직 커밋되지 않은 데이터를 덮어쓴다. 거의 모든 트랜잭션 구현은 더티 쓰기를 방지한다
           - 읽기 스큐(비반복 읽기): 클라이언트는 다른 시점에 데이터베이스의 다른 부분을 본다. 이 문제를 막기 위한 해결책으로 트랜잭션이 어느 시점의 일관된 스냅샷으로부터 읽는 스냅샷 격리를 가장 흔히 사용한다. 스냅샷 격리는 보통 다중 버전 동시성제어(MVCC)를 써서 구현한다.
           - 갱신 손실: 두 클라이언트가 동시에 read-modi-write 주기를 실행한다. 한 트랜잭션이 다른 트랜잭션의 변경을 포함하지 않은 채로 다른 트랜잭션이 쓴 내용을 덮어서 데이터가 손실된다. 스냅샷 격리 구현 중 어떤 것은 이런 현상을 자동으로 막아주지만 그렇지 않은 것은 수동 잠금이 필요하다(Select for Update)
           - 쓰기 스큐: 트랜잭션이 무언가를 읽고 읽은 값을 기반으로 어떤 결정을 하고 그 결정을 데이터 베이스에 쓴다. 그러나 쓰기를 실행하는 시점에는 결정의 전제가 더 이상 참이 아니다. 직렬성 격리만 이런 현상을 막을 수 있다.
           - 팬텀 읽기: 트랜잭션이 어떤 검색 조건에 부합하는 객체를 읽는다. 다른 클라이언트가 그 검색 결과에 영향을 주는 쓰기를 실행한다. 스냅샷 격리는 간단한 팬텀 읽기는 막아주지만, 쓰기 스큐 맥락에서 발생하는 팬텀은 색인 범위 잠금처럼 특별한 처리가 필요하다.
       - 직렬성 트랜잭션을 구현하는 세 가지 대표적인 방법으로, 트랜잭션을 순서대로 실행하기, 2단계 잠금(2PL), 직렬성 스냅샷 격리(SSI)가 있다. 직렬성 스냅샷 격리가 성능이 좋으며 낙관적 방법을 이용해 트랜잭션 차단 없이 직렬화된 격리성을 제공한다. 2PL은 과거의 표준이었으나 성능 이슈로 사용이 크게 줄었다. SSI는 다만 어플리케이션에서 경쟁조건하에서 어보트되는 트랜잭션에 대한 백오프 전략을 스스로 수행해야한다.
      
     - 8장 분산 시스템의 골칫거리
       - 분산 시스템에서는 네트워크 문제, 하드웨어 고장, 소프트웨어 문제 등으로 인해 일부 구성요소가 '항상' 예기치 않게 실패할 가능성이 있음
       - 분산 시스템 운영에는 이러한 장애에 대해 예상하고, 탐지하며, 우아하게 처리할 수 있어야함
       - 네트워크는 항상 신뢰할 수 없다고 여기는 것이 좋음. 결정적으로 관리할 수 없음. 이러한 문제는 곧 데이터 일관성 문제를 쉽게 야기하기도 함
       - 적절한 타임아웃, 재시도 전략, 네트워크로 인해 통신하는 자원들에 대한 적절한 설계가 필수적임
       - 시간과 관련된 문제는 분산 시스템에서 더욱 까다로운 일임
       - NTP를 사용해도 완벽한 동기화는 불가능하며, 시계 드리프트, 급격한 시간 조정 등으로 인해 시간과 관련된 버그는 항상 발생할 수 있음
       - 논리적 순서를 보장하고자 논리적 시계를 쓰는 대안적 방식을 많이 사용함(벡터 클록, 램포트 타임스탬프 같은)
       - 프로세스는 항상 멈출 수 있음. GC, OS 작업, 혹은 데이터센터의 문제 등..
       - 이를 위해 일부 프로세스가 고장나더라도 이를 대비할 수 있는 시스템 디자인과 합의 시스템, 복구 자동화 등이 필요함. 복구되기 전 까지 모든 시스템이 장애상태에 놓이는 것은 최악의 결과임. 분산시스템을 쓰는게 이익이 되는 규모의 서비스에서는 더더욱!
       - 분산 시스템에서 어떤것이 진정한 진실인지를 정의하는 것은 매우 어려움. 노드 간 시스템 상태는 오로지 불완전한 네트워크를 통해서만 이해할 수 있으며, 이러한 관점에서 진실값이 무엇인가에 대해 분산 노드끼리 합의에 도달하게 하는 것은 근본적으로 까다로운 문제. 다양한 합의 알고리즘이 존재하지만 트레이드오프가 있음. 대체로 과반 이상의 다수결을 기준으로 많이 해결함.
       - 시스템 모델과 현실은 괴리가 있으며, 동기식 모델, 부분 동기식 모델, 비동기식 모델 모두 각각의 한계가 있음. 이러한 차이를 인식하고 대응하는 것이 중요함.
       - 단일 시스템에서는 동일한 연산에 대한 결과가 결정적으로 작동하는 반면, 분산 시스템은 훨씬 더 비결정적임. 하지만 분산 시스템은 확장성 이외에도 내결함성과 짧은 지역 지연시간과 같은 것을 달성해야 할 때에도 필요할 수 있음.
       - 네트워크 실패, 시계의 시차, 프로세스 크래시 등이 해결할 수 없는 자연법칙적 문제인 것은 아니다. 아주 엄격한 통제를 통해 하드웨어 자원 효율성을 낮추면 해결이 가능한 것들이 많지만, 결국 성능과 안정성 사이의 트레이드오프를 통해 선택해야만한다.

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
