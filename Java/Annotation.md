## 어노테이션이 뭔가요?

Oracle사의 Java Tutorial에서의 Annotation 정의
```text
Annotations, a form of metadata, provide data about a program that is not part of the program itself. Annotations have no direct effect on the operation of the code they annotate.

Annotations have a number of uses, among them:

    - Information for the compiler — Annotations can be used by the compiler to detect errors or suppress warnings.
    - Compile-time and deployment-time processing — Software tools can process annotation information to generate code, XML files, and so forth.
    - Runtime processing — Some annotations are available to be examined at runtime.

어노테이션은 메타데이터로써, 프로그램의 그 자체의 일부분은 아니면서 프로그램에 대한 데이터를 제공한다. 
어노테이션 자체는 어노테이션을 붙인 코드 동작에 영향을 주진 않는다.

어노테이션은 다음과 같은 상황에 쓰임:

  - 컴파일러에게 필요한 정보를 제공: 컴파일러가 에러를 감지하거나, 경고를 띄우지 않게 하기 위함
  - 컴파일/배포 시에 필요한 처리 가능: SW 개발 툴에서 어노테이션의 정보를 통해 특정 코드를 추가할 수 있음 
  - 런타임 처리 제공: 런타임에도 어노테이션의 정보를 통해 필요한 처리를 할 수 있음 (Java Reflection)
```

핵심은,
- 작성한 코드에 추가적인 정보 제공
- `compile time`, `run time`에 추가적인 처리 가능
- 비즈니스 로직에 영향을 주지 않음

## 어노테이션의 유래
처음에는 소스코드와 문서를 하나의 파일로 관리하는 것이 낫다고 생각했습니다.
그래서 주석에 소스코드에 대한 정보를 같이 저장하고 주석으로부터 `HTML`문서를 만드는 `javadoc.exe` 프로그램을 만들어서 사용했습니다. 

```java
/**
 * The common interface extended by all annotation types. Note that an
 * interface that manually extends this one does <i>not</i> define an annotation type. Also note that this interface does not itself
 * define an annotation type.
    ...
 * The {@link java.lang.reflect.AnnotatedElement} interface discusses
 * compatibility concerns when evolving an annotation type from being
 * non-repeatable to being repeatable.
 *
 * @author  Josh Bloch
 * @since   1.5
 */
public interface Annotation {
    ...
}
```
이 코드를 보시면 주석 중간중간에 `@` 태그들을 볼 수 있습니다.
미리 정의된 태그들을 이용해 정보를 저장하고, `javadoc.exe`가 이 정보를 태그정보와 구분해서 읽어 `HTML`문서를 작성해주는 방식이였습니다.

## 어노테이션 사용 방법

추가해야함
## 어노테이션 실제 내부 동작 원리

추가해야함

## 스프링의 `@Conponent` 동작 원리를 알아보자
```java
@Target(ElementType.TYPE)
@Retention(RetentionPolicy.RUNTIME)
@Documented
@Indexed
public @interface Component {
	String value() default "";
}
```
`@Component`어노테이션을 정의한 코드입니다.
이를 해석해보면, `RUNTIME`에도 `class` 파일이 유지되어서 `reflection`기술을 통해 접근하여 정보를 실시간으로 동적으로 얻을 수 있음을 알 수 있습니다.

또한, SW 개발 툴에서 어노테이션의 정보를 통해 특정 코드를 추가할 수 있기 때문에, `class`나 `method`가 어떻게 쓰일지의 경로가 결정되므로 최종적으로,

스프링 프레임워크에서는 

- `@Component`어노테이션이 적용된 클래스를 **직접 찾아** 스프링 빈에 추가한다는 경로로 쓰일 것이며, 

- 추가로 동적으로 기타 정보들에 접근해 사용될 것임을 예측할 수 있습니다.

확실하진 않아서 추가로 공부해야 합니다.

## 출처
https://docs.oracle.com/javase/tutorial/java/annotations/

https://joel-dev.site/83?category=1018629

https://namocom.tistory.com/383

https://hirlawldo.tistory.com/43