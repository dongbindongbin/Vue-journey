setup() {

ref() 원시값
reactive() 참조값
-> 객체의 속성들을 자동으로 반응형으로 만들고 .value없이 바로 접근할 수 있다.
이 때 리액티브는 객체 할당을 추적하지는 않는다.
왜냐하면 주소자체가 바뀌기 때문 ref로 감싸면 추적하겠지

}

- 트리쉐이킹
  사용하지 않는 코드를 제거하는 방식

콧수염 문법
인터폴레이션
보간법
{{}}

## directives

v-접두사를 가진 특수한 속성으로 HTML요소에 특정 기능을 부여한다.

v-on:

v-bind :
v-bind:속성="동적 데이터"
v-model:

v-html: RAW HTMl 출력
v-html=""
이때 자식 html요소들을 모두 덮어씌운다.

:class= "{' ' : T,F}"

# Event Modifiers

v-on에 대한 EM을 제공해서 메서드에서 event.preventDefault()와 같은
구문을 작성하지 않도록합니다
stop prevent self
예) @submit.prevent="onSubmit"

v-model 양방향 동기화
but IME 필요한 언어의 경우 제대로 업데이트 되지 않음
-> v-on v-bind 방법을 사용해야 함

v-on Modifier
.stop 이벤트 전파 중지
.prevent 기본 이벤트 방지
.capture: 캡처링 단계에서 이벤트 수신
.self: 이벤트가 해당 요소에서만 발생할 때 처리
.once: 한 번만 이벤트 수신

v-bind Modifier
.prop: 속성을 prop으로 바인딩
.camel: 카멜 케이스 변환

- prevent form
<form @submit.prevent="changeStyle">

### return 실수 주의

## Computed properties

computed() Vue의 함수
이미 계산된 값을 리턴
반응형 데이터를 기반으로 캐시 된다.
따라서 데이터가 변경되었을 때만 eval됨

method()는 항상 호출됨

computed()와 method()는 같은 메커니즘

v-if="name === ?"

v-else:

v-else-if:

표현식의 값

<template> 페이지가 로드될 때 렌더링 x
하지만 나중에 js를 통해 사용할 수 있게함
보이지 않는 래퍼

v-text
문자열

v-show="is-seen"
v-for="(person, ?, ?) in people" div태그 안에 속성을 넣으면 그만큼 반복된다.
:key="" 왜? 렌더링 할 때 아이디로 구분하기 위해
기존 엘리먼트를 재사용하고 재정렬할 수 있도록 힌트를 제공
in-place patch

1.배열 반복 2.객체 반복 3.여러요소 반복
if가 for보다 더 높은 우선 순위

삼항연산자 가능 ""안 자동 언래핑

watch(반응데이터, 콜백함수)
-> 반응형 데이터를 감시하고 감시하는 데이터가 변경되면 콜백함수 호출
이떄 ref로 감싼 객체는 주소를 감시한다 주의!

computed watch 둘다 원본데이터를 직접 변경하지 않는다.

## 라이프 사이클 훅

이 훅에 등록된 콜백 함수들을 인스턴스와 자동으로 연결함
셋업함수 안에 있다.

## 스타일가이드
