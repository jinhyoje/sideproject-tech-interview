# OAuth 2.0

- OAuth 2.0(Open Authorization 2.0, OAuth2)은 인증을 위한 개방형 표준 프로토콜이다.
- OAuth는 인터넷 사용자들이 비밀번호를 제공하지 않고 다른 웹사이트 상의 자신들의 정보에 대해 웹사이트나 애플리케이션의 접근 권한을 부여할 수 있는 공통적인 수단으로서 사용되는, 접근 위임을 위한 개방형 표준이다.

#### OAuth 구성요소

1. Resource Owner
   - 웹 서비스를 이용하려는 유저, 자원(개인정보)을 소유하는 자, 사용자
2. Client
   - 자사 또는 개인이 만든 애플리케이션 서버
3. Authorization Server
   - 권한을 부여(인증에 사용할 아이템을 제공주는)해주는 서버다.
   - 사용자는 이 서버로 ID, PW를 넘겨 Authorization Code를 발급 받을 수 있다.
   - Client는 이 서버로 Authorization Code을 넘겨 Token을 받급 받을 수 있다.
4. Resource Server
   - 사용자의 개인정보를 가지고있는 애플리케이션 (Google, Facebook, Kakao 등) 회사 서버
5. Access Token
   - 자원에 대한 접근 권한을 Resource Owner가 인가하였음을 나타내는 자격증명
6. Refresh Token
   - Client는 Authorization Server로 부터 access token(비교적 짧은 만료기간을 가짐) 과 refresh token(비교적 긴 만료기간을 가짐)을 함께 부여 받는다.
   - refresh token을 통해 access token을 재발급 받아 재 로그인 할 필요없게끔 한다.

### 어플리케이션 등록

- OAuth 2.0 서비스를 이용하기전에 선행되어야 하는 작업
- Client를 Resource Server 에 등록
- Redirect URI 등록

#### Redirect URI

- 사용자가 OAuth 2.0 서비스에서 인증을 마치고 사용자를 리디렉션시킬 위치
- OAuth 2.0 서비스는 인증이 성공한 사용자를 사전에 등록된 Redirect URI로만 리디렉션 시킨다.
- Redirect URI는 기본적으로 보안을 위해 https만 허용된다.

#### Client ID, Client Secret

- 등록과정을 마치면, Client ID와 Client Secret를 얻을 수 있다.
- 발급된 Client ID와 Client Secret은 액세스 토큰을 획득하는데 사용된다.

# OAuth 2.0의 동작 메커니즘

1 ~ 2. 로그인 요청

- Resource Owner가 우리 서비스의 '구글로 로그인하기' 등의 버튼을 클릭해 로그인을 요청한다.
- Client는 OAuth 프로세스를 시작하기 위해 사용자의 브라우저를 Authorization Server로 보내야한다.
- 클라이언트는 이때 Authorization Server가 제공하는 Authorization URL에 response_type , client_id , redirect_uri , scope 등의 매개변수를 쿼리 스트링으로 포함하여 보낸다.

```
https://authorization-server.com/auth?response_type=code
&client_id=29352735982374239857
&redirect_uri=https://example-app.com/callback
&scope=create+delete
```

3 ~ 4. 로그인 페이지 제공, ID/PW 제공
- 클라이언트가 빌드한 Authorization URL로 이동된 Resource Owner는 제공된 로그인 페이지에서 ID와 PW 등을 입력하여 인증할 것 이다.

5 ~ 6. Authorization Code 발급, Redirect URI로 리디렉트
- 인증이 성공되었다면, Authorization Server 는 제공된 Redirect URI로 사용자를 리디렉션시킬 것 이다.
- Redirect URI에 Authorization Code를 포함하여 사용자를 리디렉션 시킨다.
- Authorization Code란 Client가 Access Token을 획득하기 위해 사용하는 임시 코드이다. 이 코드는 수명이 매우 짧다. (일반적으로 1~10분)

7 ~ 8. Authorization Code와 Access Token 교환
- Client는 Authorization Server에 Authorization Code를 전달하고, Access Token을 응답받는다.
- Client는 발급받은 Resource Owner의 Access Token을 저장하고, 이후 Resource Server에서 Resource Owner의 리소스에 접근하기 위해 Access Token을 사용한다.

9. 로그인 성공
- 위 과정을 성공적으로 마치면 Client는 Resource Owner에게 로그인이 성공하였음을 알린다.

10 ~ 13. Access Token으로 리소스 접근
- 이후 Resource Owner가 Resource Server의 리소스가 필요한 기능을 Client에 요청한다. 
- Client는 위 과정에서 발급받고 저장해둔 Resource Owner의 Access Token을 사용하여 제한된 리소스에 접근하고, Resource Owner에게 자사의 서비스를 제공한다.




