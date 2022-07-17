## `reflection`이 뭐에요

**객체를 통해 클래스의 정보를 분석해 내는 프로그램 기법**이다.

즉, 구체적인 클래스 타입을 알지 못해도 그 **클래스의 정보(메서드, 타입, 변수 등등)**에 접근할 수 있게 해주는 자바 API 이다.

## 어떻게 동작하나요?

1. `.java`파일을 자바 컴파일러를 통해 `.class`인 바이트코드로 변환한다.
2. 바이트코드를 `classLoader`를 통해 `Class`클래스에 정의된 형식으로 변환되어 메모리에 로딩하게 된다.
3. 이 `Class<T>`인스턴스에 접근하면 된다.

![image](https://user-images.githubusercontent.com/105288887/179418633-631c786b-d21c-483b-909a-47ea5c4023c4.png)

자세한 동작 방식은 JVM 동작 방식에서 설명하겠다.

중요한 것은 컴파일 단계에서 동작하는 것이 아닌, **런타임에 동적으로 타입을 분석하고 정보를 가져온다는 점이다.**

## 어떻게 사용하나요?

- 클래스 리터럴로부터 얻는 방법
  
  `타입.class`, 이는 곧 `Class<타입>`과 같은 의미이다.
```java
ApplicationContext ac = new AnnotationConfigApplicationContext(AppConfig.class);
```
- 생성된 객체로부터 얻는 방법
  `java.lang`에서 `Object`클래스의 메소드 중 하나인 `인스턴스.getClass()`로 접근 할 수 있다.
```java
Class obj = new Card().getClass();
```
- 클래스 이름으로부터 얻는 방법
  `Class.forName("클래스 이름")을 통해 클래스 이름으로 읽어올 수 있다.
```java
Class obj = Class.forName("Card")
```

## 어디에 쓰이나요?

- 필드 (목록) 가져오기
- 메소드 (목록) 가져오기
- 상위 클래스 가져오기
- 인터페이스 (목록) 가져오기
- 애노테이션 가져오기
- 생성자 가져오기

이러한 기능을 수행할 수 있다.

주로 어플리케이션 개발보다 프레임워크에서 많이 사용하게 된다.

대표적으로 SpringContainer에서 BeanFactory에서 Bean은 **런타임 시에 동적으로 인스턴스를 생성**하는데 이때 Reflaction API가 사용된다. 사용자가 클래스를 만들어주지 않고 동적으로 만들어야 되기 때문이다.

이외에 intellij의 자동완성기능, Spring Data JPA에서 Entity 등 다양한 곳에 사용되고 있다.

## 참고

자바 공식 문서
https://docs.oracle.com/javase/8/docs/api/java/lang/Class.html

Tecoble

https://tecoble.techcourse.co.kr/post/2020-07-16-reflection-api/

블로그
https://docs.oracle.com/javase/8/docs/api/java/lang/Class.html

https://velog.io/@devsigner9920/Java-Reflection-API-01

자바의 정석 3판 챕터 9
