## 왜 등장했을까

기존 for문은

```java
for(int i=0; i < arr.length; i++){
    System.out.println(arr[i]);
}
```

이런식으로 작성했다면

향상된 for문은 

```java
for(int tmp : arr) {
    System.out.println(tmp);
}
```

더 **간결하게 작성됨**을 알 수 있다.

즉, 배열과 컬렉션에 저장된 요소에 접근할 때, 기존보다 편리한 방법으로 처리할 수 있도록 추가된 문법이다.

## 어떻게 쓰는걸까

```java
for( 타입 변수명 : 배열 또는 컬렉션 ) {
    // ~~
}
```

이렇게 쓰면 된다.

주의할 점은

배열(`array`) or 컬렉션(`Collection`)에 저장된 **요소들을 읽어오는 용도**로만 사용할 수 있다는 것이다.

## 출처

자바의 정석 3판 남궁성