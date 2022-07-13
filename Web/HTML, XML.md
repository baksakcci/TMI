## `XML`이 뭔가요?

xml을 알기 위해서는 markup language의 역사를 알아야 한다.

그 전에 markup에 대해서 알아보자

## `markup`은 뭔가요?

- 문서의 활자나 조판을 지정하는 표시
- 태그 등을 이용하여 문서나 데이터의 구조를 나타내는 것

원고를 인쇄할 때, 임시로 인쇄물을 찍고 편집자가 이걸 검토하여 교정작업을 진행한다. 이떄, 임시 인쇄물을 검토하면서 **잘못된 부분에 표시를 해두는게 markup**.

컴퓨터에서도 문서를 작성하고 보여주는 역할에 충실했는데, 이때 나온 것이 markup language이다. **태그**가 바로 위에서 나온 **표시하는 역할**이 되는 것이다.

## hyper link, Hyper Text 간단 설명

hyper의 뜻은 뭘까

`~를 넘어서는`, `~을 훨씬 능가하는`; `정상보다 지나치게 많은`, `과도한`

**hyper link**는 뭘까

`순서를 넘어서는 연결`

순서에 상관없이 링크된 곳을 클릭만 하면 바로바로 원하는 문서로 넘어갈 수 있는 것이다.

나무위키 생각하면 쉽다.

**Hyper Text**

`hyper link 기능이 삽입된 문서`

문서 내 특정 단어에다가 `link`기능을 넣어줌으로써 문서와 문서를 연결시켰다.

관련있는 정보들을 찾아갈 수 있도록 만든 구조로, 정보의 **검색과 관리**를 쉽게 하기위함이다.

**hyperlink + 컴퓨터의 특성 중 쌍방향성**

이제 Hyper Text의 역사를 알아보자

## `SGML`의 등장

Standard Generalized Markup Language 표준 마크업 언어 규약

컴퓨터용 전자 문서의 작성에 관한 국제 표준 규약이다.

문서용 마크업 언어를 정의한 **메타 언어**

```
<!DOCTYPE mod [ <!E~~ 잘모름
<motd>
<!-- created: 2003-12-12-->
	<sentence>Do not throw out the <keep>baby</>
	<refuse>dirty</>,
	<refuse>stinky</>,
	<refuse>bathwater</>,
	</>
	<!-- finish this later -->
<motd>
```

## `SGML`의 후속작 `HTML`의 등장

Hyper-Text Markup Language

문서의 글자모양, 그림, 영상, 문서이동 등을 지정하는 명령어(`tag`)이다. 

Hyper Text를 작성하기 위해서 개발된 언어로 `SGML`을 기반으로 제작되었다.

인터넷을 통해서 공유하여 문서를 보고자 웹용 문서작성 방법을 만들 생각을 했는데, `SGML`이 너무 좋아서 여기서 불필요한 것들만 빼고 만든 언어이다.

이후 WC3에서 `HTML`을 다양한 브라우저에서 공통적으로 사용할 수 있도록 표준을 정의해나가면서 **웹페이지를 위한 마크업 언어**로 자리잡게 되었다.

즉, **`HTML`은 웹페이지를 표현하는데 목적을 둔 마크업 언어**이다.

```html
<!DOCTYPE html>
<html>
    <head>
        <title>HOME</title>
        <meta charset="UTF-8"/>
    </head>
	<body>
		<h1>My First Heading</h1>
		<p>My first paragraph.</p>
	</body>
</html>
```

`HTML`을 전송하고 `HTML`을 받는 통신 프로토콜이 `HTTP`이다

`HTTP`는 다른 페이지에 따로 설명할 예정이다.

## `SGML`의 또다른 후속작 `XML` 등장

eXtensible Markup Language

서버간에 데이터를 전송할 때 HTML 1.0은 SGML을 기반으로 받을 자료를 정의한 뒤 주고받았는데, 이는 너무 느리고 무거웠다.

이를 위해서 SGML의 장점만 가지고 XML이 개발되는데, 이를 통해 HTML의 정보를 디테일 하게 표현하여 전송이 가능해졌다.

즉, XML은 **데이터 교환을 위한 구조 정의에 목적을 둔 마크업 언어**이다.

```xml
<title>제목입니다</title>
<content>내용입니다</content>
<sender>발송자</sender>
```

## 이 둘이 차이점은 뭘까?

- 데이터의 표현, 데이터 교환을 위한 구조정의
- 정해진 태그, 사용자 태그 정의
- 인터넷 웹 환경에서 작동, 특정 환경 구애 X
- 데이터 표현 동시에, 데이터만을 가짐

지속적인 업데이트가 필요,,,내가 이해한 것이 맞는지도 모르겠다.

## 출처

HTML과 XML 차이 - https://www.crocus.co.kr/1493

SGML / HTML / XML - https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=kimone0915&logNo=150119128236

Restful에 대한 이해하기(웹의 역사) - 1 - https://hwan-shell.tistory.com/139?category=826872

Restful에 대한 이해하기(xml, soap란?) - 2 - https://hwan-shell.tistory.com/140

HTML과 XML의 차이점 - https://hanamon.kr/htm-xml-%EC%B0%A8%EC%9D%B4%EC%A0%90/

XML 나무위키 - https://namu.wiki/w/XML