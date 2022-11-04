# 네트워크
---
<details>
<summary>인터넷은 어떻게 동작하나요?</summary>
<div markdown="1">
  <br>
인터넷은 TCP/IP 프로토콜을 사용해 형성된 네트워크를 의미합니다.<br>
이 말을 이해하기 위해선 TCP/IP프로토콜에 대해서 그리고 네트워크에 대해서 이해가 수반되어야하는데요. <br>
TCP/IP프로토콜이란 컴퓨터와 컴퓨터 사이에 데이터를 주고받을때 사용하는 일종의 규약입니다. <br>
또한 네트워크는 컴퓨터와 컴퓨터가 그물망 처럼 연결된 형태를 의미합니다.<br>
처음에 컴퓨터와 컴퓨터는 물리적으로 연결이 돼야했습니다. <br>
하지만 그런 점이 매우 불편하기 때문에 라우터가 등장했어요. <br>
라우터는 컴퓨터와 컴퓨터사이의 연결만을 해주는 작은 컴퓨터라고 볼 수 있어요.<br>
라우터가 한대 중심에 있고 컴퓨터는 라우터 한대에 연결을 하죠.<br>
그리고 라우터는 요청을 받아서 제대로 된 목적지까지 전송을 해줍니다.<br>
하지만 이런 라우터를 설치하더라도 장거리에 있는 라우터와 라우터를 연결해야할 일이 생깁니다.<br>
우리의 조상들은 이 라우터를 연결하는 것 말고, 기존의 전화선을 사용하기로 결정합니다.<br>
기존의 전화선을 사용하기 위해선 전화신호와 네트워크 신호를 변환해주는 기계가 필요하고, 그 기계가 모뎀입니다.<br>
컴퓨터는 라우터에 연결이 되고, 라우터는 모뎀에 연결이 되고, 모뎀은 그 신호를 아날로그 신호로 바꾸어서 이미 설치되어있는 전화기기 사이에 통신을 합니다. <br>
그리고 현 네트워크에서 도달하려는 네트워크로 신호를 보내기 위해 ISP로 연결을 해주어야합니다. <br>
그렇게 되면 우리가 현재 인터넷이라고 부르는 형태에 매우 가까워지게 됩니다.<br>
</div>
</details>
<details>
<summary>TCP, UDP, 3way handshake, 4way handshake에 대해 설명해 보세요 </summary>
<div markdown="2">
  <br>
TCP와 UDP는 전송계층의 프로토콜중 잘 알려진 프로토콜입니다.<br>
TCP는 UDP와는 다르게 연결을 지향하는 프로토콜로 핸드쉐이킹 방식을 이용해서 서로의 연결이 잘 되었음을, 잘끊겼음을 확인하는 과정이 들어가게 됩니다.<br>
그렇기 때문에 UDP보다는 느리다는 단점이 있습니다. <br>
하지만 높은 신뢰성을 유지하기 때문에 신뢰성이 필요한 곳에서 TCP를 사용합니다. <br>
그 외에도 흐름제어나 혼잡제어같은 일을 합니다. <br>
흐름제어는 받는쪽 버퍼 오버플로우를 방지하기 위해 데이터 처리 속도를 제어하는 것이고, <br>
혼잡제어는 전송하는 패킷수를 조절하여 혼잡이 일어나는 것을 막는 일입니다. <br>
UDP는 그에 반해 데이터를 받았음을 확인하는 과정이 없습니다. <br>
그렇기때문에 신뢰성은 낮지만 빠르다는 장점이 있습니다. <br>
그래서 UDP는 신뢰성보단 연속성이 중요한곳에 쓰입니다.<br>
3 way handshake는 TCP의 연결을 초기화할때 사용합니다. <br>
연결 요청에 대한 SYN을 보내고 그에 대한 답장으로 SYN에 1을 더해서 ACK와 함께 답장을 보냅니다. 그리고 또 그에 대한 답장으로 ACK를 보냅니다.<br>
4 way handshake는 세션을 종료하기 위해 사용됩니다. Client가 FIN 패킷을 보내면 서버는 FIN을 잘받았다는 의미로 ACK를 보냅니다.<br>
그리고 서버는 남은 데이터들을 다 보냈을때 FIN을 보냅니다. client는 서버에게로부터 FIN이 도착하면 잘받았다는 의미로 ACK를 보내게 됩니다.<br>
</div>
</details>

<details>
<summary>흐름제어와 혼잡제어에 대해 좀 더 자세히 설명해주세요 </summary>
<div markdown="3">
  <br>
흐름제어는 sender와 receiver의 데이터 처리 속도 차이를 제어하기 위한 기법으로, receiver의 버퍼가 감당할 수 없는 속도로 데이터가 전송되어 버퍼 오버플로우가 <br>
생기는 것을 방지하기 위해 데이터 전송 속도를 제어하는 것이 흐름제어이다..<br>
<br>
혼잡제어는 sender의 데이터 전달 속도와 네트워크 데이터 처리 속도 차이를 해결하기 위한 기법이다.<br>
한 라우터에 데이터가 몰려 모든 데이터를 처리할 수 없는 경우, 각 sender들은 데이터를 라우터에 재전송 하게되고 이로인해 혼잡이 가중되어 오버플로우나 데이터 손실이 발생한다.<br>
이와 같은 네트워크 혼잡을 방지하기 위해 sender의 데이터 전송 속도를 제어하는 것이 혼잡제어이다.<br>
<br>
흐름제어와 혼잡제어의 차이는 결국
호스트(컴퓨터)와 호스트간의 데이터 처리인가, 호스트와 네트워크 상의 데이터 처리인가의 차이.<br>
</div>
</details>

<details>
<summary>TCP와 HTTP의 관계</summary>
<div markdown="4">
  <br>
HTTP는 응용계층 프로토콜, TCP는 전송계층 프로토콜이다. HTTP는 TCP 기반 위에서 만들어졌기 때문에 TCP 성격을 모두 포함한다.<br>
</div>
</details>

<details>
<summary>HTTP란 무엇인가요?</summary>
<div markdown="5">
  <br>
HTTP는 TCP/IP위에서 동작하는 텍스트 기반의 통신규약입니다. <br>
HTTP는 연결상태를 유지하지 않는 비연결성 프로토콜입니다. 이러한 단점을 극복하기 위해 세션이나 쿠키 등을 활용합니다 <br>
</div>
</details>

<details>
<summary>HTTP는 어떻게 동작하나요?</summary>
<div markdown="6">
  <br>
먼저 사용자가 웹브라우저에 URL을 입력합니다.<br> 그러면 DNS로 요청이 가게되는데요 그래서 도메인 이름을 IP주소로 바꿔줘서 그 주소로 요청이 가게 됩니다.<br> 웹서버와 TCP연결을 시도하게 되고, 연결됐음을 확인한 이후에 클라이언트가 서버에게 HTTP 요청을 하게 됩니다. <br>서버는 클라에게 응답을 보내게 되고 응답이 끝났음을 확인하면 TCP연결을 끊게 됩니다. 이걸 매번 반복합니다. <br>
</div>
</details>

<details>
<summary>네트워크 4계층의 각각의 프로토콜에 대해서 설명해주세요</summary>
<div markdown="7">
  <br>
클라이언트와 서버에 해당하는 컴퓨터 두개를 가져왔다 그리고 이 둘을 케이블로 연결한다<br>
그럼 이때 사용되는 계층이 네트워크 인터페이스 계층이다<br>
하지만 둘이 매우 멀리 떨어져있다고 가정하다. 이때 인터넷이 필요하고 인터넷은 케이블의 역할을 대신한다<br>
이때 인터넷 계층이 필요하다 즉, 인터넷을 거쳐야한다<br>
하지만 이렇게 인터넷계층으로만 통신을 하다보면 한계가 있다. 비연결성과 비신뢰성에있다<br>
비연결성 - 연결되어있지 않은 상태여도 패킷을 전송한다<br>
비신뢰성 - 중간에 패킷이 사라지거나 순서대로 오지 않아도 이런부분에 대해 체크를 하지 않는다<br>
프로그램 구분 - 같은 ip를 사용하는 서버에서 통신하는 애플리케이션이라면 둘을 어떻게 구분할 것인가?<br>
이러한 IP 프로토코르이 한계를 극복하는 방법이 TCP프로토콜이다<br>
그래서 TCP를 계층이 추가된다. 그러니까 인터넷계층까지로만 통신을 하다보면 비연결성과 비신뢰성 등 여러 문제가 생기는데 전송계층까지로 범위를 넓혀서 사용하게되면
이 문제를 해결할 수 있다 <br>
</div>
</details>

# JPA
---
<details>
<summary>JDBC란</summary>
<div markdown="8">
  <br>
  자바애플리케이션과 디비의 통신을 가능하게 해주는 API
<br>
</div>
</details>

<details>
<summary>JDBC와 MyBatis의 차이</summary>
<div markdown="8">
  <br>
JDBC한 파일에서는  SQL작성, DB연결, Java언어가 모두 존재하기때문에 재사용성이 좋지 않다. 하지만 마바는 SQL문과 자바언어를 분리한다
<br>
JDBC에서는 매번 파라미터 매핑을 해줬어야하는데 마바에서는 자동으로해준다
<br>
</div>
</details>

<details>
<summary>직렬화와 역직렬화 차이</summary>
<div markdown="8">
  <br>
  직렬화: 객체를 전송가능한 연속적인 데이터로 만드는것<br>
  역직렬화: 연속적인데이터 -> 객체 변환
<br>
</div>
</details>

<details>
<summary>데이터베이스와 자바의 패러다임의 차이에 대해 설명해주세요</summary>
<div markdown="8">
  <br>
  1. 상속구현방법<br>
  - 자바는 객체지향패러다임을 이용해서 상속을 구현합니다. 하지만 디비에는 이러한 상속개념이 없죠. <br>
  - 자바에서는 우리가 배웠던 방식대로 상속을 하면된다. <br>하지만 디비에서는 상속의 개념이 없다. 예를들어 상속을 하려면
한테이블에 모두 데이터를 몰아넣는방식이나 여러 테이블을 둬서 하나의 데이터를 저장할때 상속관계인 테이블 각각에 insert쿼리를 날리는
불편한 작업을 해야한다.<br>이건 jdbc를 쓸때의 애기고 jpa를 만약 사용한다면 save메서드하나로 상속관계인 테이블 각각에 insert쿼리를 알아서 날려줄 수 있다<br>
즉, 개발자는 save메서드만 호출하고 jpa가 알아서 insert쿼리를 만들어서 디비로 요청을 보낸다는것이다. 그게 가능하다<br>
  2. 참조<br>
  - 자바에서는 객체를 참조할 수 있습니다. 디비는 fk로 참조를 대신합니다<br>
  - 자바에서의 객체는 참조를 통해서 연관관계에 있는 객체를 조회하고 탐색한다.<br>
반면에 디비의 테이블은 외래키를 사용하여 다른테이블과 연관관계를 맺고 조인을 사용해서 연관된 테이블을 조회할 수 있따<br>
우리가 디비의 패러다임에 맞춰서 id값을 필드로 저장하게되면 작성할땐 편리하지만 참조를 이용해야할땐 불편하다<br>
id값으로 조회를 매번 해와야하기 때문이다. 이러게 되면 객체지향적인 코드라고 할 수 없다<br>
그렇다고 id값이 아닌 team이라는 entity자체를 필드에 넣기에는 디비에 넣을때마다 매번 getid를 해주어야한다.<br>
참조에서도 패러다임의 불일치가발생하고 있다. 이를 해결해주는 것이 jpa다. <br>
  3. 비교<br>
  - 객체는 마음껏 객체그래프를 탐색할 수 있어야하는데 쿼리문에 따라서 그 객체가 있을수도있고 없을 수도 있어요
그래서 마음껏 객체 그래프를 탐색하는게 힘들어요 그 값이 있을지 없을지 모르니까요<br>
  4. 객체그래프탐색<br>
  - 디비에서는 식별자로 각 row를 구분하는데 자바에서는 동등성, 동일성비교를 할 수 있어요
<br>
</div>
</details>

<details>
<summary>JPA, ORM에 대해 설명해보세요</summary>
<div markdown="8">
  <br>
  - 마바까지 섞어서 얘기해보자면, 마바는 쿼리문의 결과를 객체에 매핑하는 sql mapper의 기술의 예고 jpa는 테이블을 객체에 매핑시키는 orm기술의 예예요<br>
  - 위에서 얘기했던 패러다임의 불일치 문제를 개발자 대신 해결해주는게 orm입니다<br>
<br>
</div>
</details>

<details>
<summary>식별과 비식별의 차이, 장단점</summary>
<div markdown="8">
  <br>
  식별: 부모의 pk를 fk로 사용하는것<br>
  비식별: 부모의 pk를 자신의 pk로도 사용하는것<br>
  식별관계는 조인할때 키의 수가 늘어나니까 복잡해진다. 그리고 식별관계를 구현하려면 번거롭다. 하지만 특정상황에서 조인없이 탐색할 수 있다 예를들면 부모id값이 2 인 모든 자식 조회하는일
<br>
</div>
</details>

<details>
<summary>변경감지가 일어나면 무슨일이 일어나나요?</summary>
<div markdown="8">
  <br>
  1. flush()메서드가 호출되면 .. <br>
  2. 스냅샷과 비교하여 달라진 부분은 쓰기지연저장소로 보낸다 <br>
  3. 디비에 flush한다 <br>
  4. 디비에 commit한다 <br>
  - flush:쓰기지연저장소에 있는 것들을 디비에 반영한다는 얘기. 하지만 commit까지 완료가 돼야 디비에 완전히 반영됨<br>
<br>
</div>
</details>

<details>
<summary>em.persist후 jpa가 무슨일을 해주나요?</summary>
<div markdown="8">
  <br>
 entity분석<br>
sql문 작성<br>
JDBC API사용<br>
페러다임불일치해결<br>
<br>
</div>
</details>

<details>
<summary>스프링에서 프록시가 어떻게 활용되나요?</summary>
<div markdown="8">
  <br>
  프록시 객체는 가짜객체를 의미합니다. 매번 연관된객체를 불러오는것보다 실제사용시점까지 불러오는것을 미루면 성능상 이점이 있습니다.<br>
<br>
</div>
</details>

<details>
<summary>em.find와 em.reference는 무슨차이가 있나요?</summary>
<div markdown="8">
  <br>
 em.find:메서드 호출하자마자 디비에 조회쿼리날림 <br>
 em.reference:사용시점에 디비에 쿼리날림
<br>
</div>
</details>

<details>
<summary>em.reference가 호출될때 무슨일이 일어나나요?</summary>
<div markdown="8">
  <br>
 db를 조회하지도, 실제 엔티티객체를 생성하지도 않는다. 실제 엔티티객체를 상속받은 프록시 객체를 만들 뿐이다.
<br>
</div>
</details>

<details>
<summary>em.reference로 찾은 엔티티에 대해 참조를 하면 무슨일이 일어나나요?</summary>
<div markdown="8">
  <br>
 1. 영속성컨텍스트에 초기화요청
 2. 영속성컨텍스트에 없다면 디비로 요청해서 초기화해와서 실제 엔티티객체를 생성해온다 
<br>
</div>
</details>

<details>
<summary>em.reference하고 얻은 엔티티에 대해 getId를 했는데 초기화가 안일어나 왜그러지?</summary>
<div markdown="8">
  <br>
 id는 프록시 객체도 기억하고 있다. 그래서 초기화가 일어나지않는다 그래서 연관관계 설정할땐 id값만 필요하니 이땐 초기화과정이 필요가 없다
<br>
</div>
</details>

<details>
<summary>jpa의 영속성 전이에 대해 설명해주세요</summary>
<div markdown="8">
  <br>
 flush시 영속성 전이가 일어납니다. 그래서 연관되어있다면각각에 대해 쿼리를 만들어서 jpa가 디비에 대신 요청해줍니다
<br>
</div>
</details>
