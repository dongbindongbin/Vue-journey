## Component

-컴포넌트

<script setup>
import ButtonCounter from './ButtonCounter.vue'
</script>

<template>
  <h1>아래에 자식 컴포넌트가 있습니다.</h1>
  <ButtonCounter />
</template>

스크립트 셋업을 사용하면 가져온 템플릿을 자동으로 사용할 수 있다.
전역으로 등록하면 임포트할 필요없이 지정된 앱의 모든 곳에서 사용할 수 있다.

## Props

부모 pass props 이벤트 리슨
자식 $emit events props 전달 받음

모든 props는 하향식 단방향 바인딩을 형성
부모 속성이 업데이트 되면 자식으로 흐름

import defineProps({
const props = { // 객체 방식으로 정의 하는 것을 권장한다. 문자열 배열 형식 보다.
type: Array,
required: true
}
})

## 버블링

특정 화면 요소에서 이벤트가 발생했을 때 해당 이벤트가 더 상위의 화면 요소들로 전달 되어가는 특성을 의미한다

## 캡처링

부모 요소에서 자식 요소로 이벤트가 전파되는 방식 캡처링은 버블링과 반대 방향으로, 이벤트가 가장 상위 부모 요소(예: document, body)에서 시작하여, 자식 요소(예: 버튼)까지 내려간다.

## 핫 모듈 리플레이스먼트 (HMR)

SPA에서 하나의 app.js로 모든 것을 로드한다.
이때 refresh하면 모든 부분의 데이터가 초기화 되어 버린다.

따라서 전체를 갱신하지 않고 변경한 모듈만 바꿔 주는 웹팩 개발서버의 기능이다.
