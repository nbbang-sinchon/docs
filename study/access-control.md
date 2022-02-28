# 접근제한라우팅

### 프론트에서 유저가 로그인 됐는지 확인하려면? 그리고 그에 따른 라우팅은?

![](https://i.imgur.com/jXgMNko.png)

-   라우팅 전 프론트에서는 사용자의 쿠키나 Storage를 조회하여 토큰이 있는지 검사한다.
-   그리고 그에 따라 유저에게 다른 페이지를 보여준다.
-   이걸 제한 접근 라우팅이라 한다.

### 로그인여부에 따른 라우팅
![](https://i.imgur.com/2CBQPiX.png)

-   서비스 마다 다르지만 로그인여부에 따라 리디렉션을 해주는게 바람직하다.
-   예를들어 마이페이지에 들어갔는데 로그인이 안되있다면 로그인페이지로 리디렉션

### 구현
-   App.jsx의 Router 컴포넌트 안에 PrivateRoute 컴포넌트와 PublicRoute 컴포넌트를 추가한다.
-   각각의 루트 컴포넌트 안에 로그인을 검증하는 isLogin()함수를 삽입하여 Rendering할 것인지, 혹은 Redirection할 것인지 판별한다.
-   PrivateRoute 컴포넌트는 로그인 페이지로, PublicRoute 컴포넌트는 메인 페이지로 Redirection한다.

### Reference
https://cotak.tistory.com/108