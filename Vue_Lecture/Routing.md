## Routing

네트워크에서 경로를 선택하는 프로세스
클라이언트 측에서 수행 SSR 

1페이지 여러 컴포넌트

라우팅이 없다면?
새로 고침시 첫 페이지
공유도 첫 페이지
뒤로가기도 안됨

뷰에서 공식으로 제공해 줌

## How
<RouterLink 속성 to="{name: 'home'}" >
<RouterView/> 컴포넌트
a 태그로 렌더링

to속성 동적 바인딩 가능
어떻게? 객체 형태로 키-밸류
{name: 'home'}
왜? named? 하드 코딩 된 URL을 사용하지 않아도 됨

<RouterView>자리에 갈아 끼워짐
이 두개의 컴포넌트는 전역에 등로되어있음 from 'vue-router'


createWebHistory
const routes = createRouter({
    route: [
      {
        path: '/:id',  -> 동적으로 경로 매칭
        name: 'about',
        component: view
				children: [
					{
						path:
						name: 
						component:
					},
					{
						path:
						name:
						component:
					}
				]
      }
    ]
})

## 동적 경로 매칭
- ex-> user/:id (v-bind)
컴포넌트에서 $route.prams로 접근 가능
하지만 권장사항은 아님

그보다는 컴포지션으로 접근
userRoute()를 활용하여 라우트 정의
및 파람들 ref로 묶어서 사용

-> 똑같은 컴포넌트에서 파람이 바뀐다고 페이지 새로 렌더링 되지 않음
따라서 watch등으로 감시하는 법이 있다
watch(()=> id, (newId) => id.value = newId)

## 프로그래밍 방식 내비게이션
-router.push() 다른 위치로 이동 하기
스택에 쌓는다 라우트 링크 누른 to와 같음
어떻게 해야함? router useRouter from 'vue-router'

parmas: {}, query: {} 넘길 수 있음

-router.replace() 현재 위치 바꾸기 -> 뒤로가기 불가

## 내비게이션 가드 (인터셉터)
뷰 라우터를 통해 특정 url에 접근할 때 
리다이렉트 하거나 접근을 취소하여 내비게이션을 보호

# Globally (전역 가드)
- router.beforeEach((to, from) => {

	return false; 
	return {name: 'login'} -> 로그인 뷰로 보냄
})

# Pre-Route (라우터 가드)
beforeEnter((to, from) => {

})
route에 진입했을 때만 실행되는 함수
라우트에 작성한다


# In-component (컴포넌트 가드)
onBeforeRouteLeave()

 
onBeforeRouteUpdate()



# createRHistory
