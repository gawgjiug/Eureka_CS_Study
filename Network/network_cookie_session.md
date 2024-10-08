![](https://velog.velcdn.com/images/gawgjiug/post/4116e816-5638-4019-88db-0c6875a70883/image.png)


#### HTTP의 특징과 쿠키와 세션을 사용하는 이유

* 쿠키와 세션을 사용하는 이유는 바로 HTTP 프로토콜의 특성이자 약점을 보완하기 위함이다

* 기본적으로 HTTP 프로토콜 환경은 `connectionless` `stateless` 한 특성을 가지기 때문에 서버는 클라이언트가 누구인지 매번 확인해야 한다. 

* 이러한 특성을 보완하기 위해서 쿠키와 세션을 사용하게 되는 것

> connectionless 란?
클라이언트가 요청을 한 후 응답을 받으면 그 연결을 끊어 버리는 특징을 말한다.
HTTP 는 먼저 클라이언트가 request 를 서버에 보내면 , 서버는 클라이언트 요청에 맞는 response 를 보내고 접속을 끊는 특성이 있다.

> stateless 란?
통신이 끝나면 상태를 유지하지 않는 특징을 말한다.
연결을 끊는 순간 클라이언트와 서버의 통신이 끝나며 상태 정보는 유지하지 않는 특성이 있다.
쿠키와 세션은 위의 두 가지 특징을 해결하기 위해 사용한다.

즉, 요청이 끝나면 서버는 유저가 누군지 잊어버리기 때문에, 요청 할 때마다. 우리가 누군지 `알려줘야` 한다는 것

이를 하는 방법 중 하나가 `세션` 임 

예를들어 `곽지욱` 이라는 유저가 있고 로그인 하고 싶다면 `유저명` 그리고 `비밀번호` 를 서버에 보내게 된다. 

비밀번호가 확인된다면 서버는 세션 DB에 `곽지욱` 이라는 유저를 생성한다 해당 세션에는 별도의 ID가 있고,

해당 세션 ID는 쿠키를 통해 브라우저로 돌아오고 저장된다. 따라서 같은 웹 사이트의 다른 페이지로 이동하면 브라우저는 세션 ID를 갖고 있는 쿠키를 서버에게 보내게 된다.

왜냐면 쿠키는 자동으로 보내지기 때문이다 

서버는 들어오는 쿠키를 보고, 해당 세션 ID를 가지고 세션 DB를 확인할 것이고 거기서 해당 ID는 유저명 `곽지욱` 의 것이라는 것 알게되고. 그때 서버는 사용자를 구분할 수 있게 된다. 

이 작업이 끝나고 다른 페이지로 이동하게 되면 이 모든 프로세스가 반복되는 것

여기서 중요한 건 모든 중요한 유저 데이터는 모두 서버에 있고 유저가 브라우저 상에서 갖고잇는 것은 세션 ID 뿐이라는 것이다.

---

#### 쿠키(Cookie)

* 쿠키란? 위에서 말했듯이 그저 세션 ID를 전달하기 위한 매개체일 뿐이다.

* 쿠키를 이용해서 서번는 나의 브라우저에 데이터를 넣을 수 있다.

* 사이트에 방문하면 브라우저는 서버에 `요청` 을 보내게 되는데, 서버는 이에 `response` (응답)을 할 것이고 , 그 `응답` 에는 모든 데이터와 내가 찾던 페이지 정보가 들어있다. 

* 또한 그곳에는 브라우저에 저장하고자 하는 쿠키가 있을 수 있는 것이다.

* 이 쿠키는 내가 브라우저에 저장해두고 해당 웹 사이트에 방문할 때 마다 브라우저는 해당 쿠키도 요청과 함께 보내게 된다.

* 참고로 쿠키는 도메인에 따라 제한이 되는데, 이 말은 즉슨 유튜브가 준 쿠키는 유튜브 서버에만 보내지게 된다는 것이다.

* 그리고 쿠키는 유효기간을 가지고 있다. 유효기간에 따라 어떤 쿠키는 하루 혹은 한달 등.. 서버가 정한 기간에 따라 유효한 특징을 가지고 있다.

---

#### 쿠키의 동작 방식 예시

그리고 쿠키는 인증 뿐만 아니라 여러가지 정보를 저장할 수 있는데, 

예를 들면 사용자가 웹 사이트 언어 설정을 바꾸면 서버는 쿠키를 브라우저에게 주고 사용자가 선택한 언어를 저장하게 된다.

따라서 다음에 내가 해당 웹 사이트에 방문할 때 쿠키는 요청과 함께 서버로 보내지고 덕분에 서버는 쿠키가 기억해둔 언어설정의 페이지를 제공할 수 있는 것이다.

---

#### 세션이란?

세션이란 이미 말했지만, 서버 측에서 사용자의 상태 정보를 관리하는 방식으로, 클라이언트와 서버 간의 지속적인 통신 상태를 유지하기 위해 사용된다. 

앞서 설명한 HTTP의 두 가지 특성으로 인해 서버는 클라이언트의 정보를 매번 새롭게 받아야 하는데,

이를 해결하기 위해 서버가 클라이언트의 정보를 일정 시간 동안 저장하여, 각 요청에서 사용자를 식벽할 수 있도록 돕는 역할을 한다고 생각하면 된다.


---

#### 세션의 동작 방식

1. 세션 생성 : 사용자가 웹에 로그인 하거나 중요한 작업을 수행할 때, 서버는 클라이언트의 정보를 서버 내부의 세션 저장소에 기록한다. 

2. 세션 ID 발급 : 서버는 클라이언트가 고유한 세션을 가질 수 있도록 세션 ID를 발급하고, 이 세션 ID는  클라이언트가 해당 서버에서 진행하는 활동을 식별하기 위한 고유 값이다. 

세션 ID는 주로 쿠키에 담겨 클라이언트 측 브라우저에 저장된다.

3. 세션 유지: 클라이언트가 웹 사이트의 다른 페이지로 이동하거나 추가적인 요청을 보낼 때, 브라우저는 자동으로 쿠키게 저장된 세션 ID를 서버로 전달한다.

4. 세션 종료 : 세션은 일정 시간이 지나면 만료되거나, 사용자가 로그아웃 하는 경우 명시적으로 삭제된다. 



