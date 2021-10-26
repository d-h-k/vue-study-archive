# 뷰 스터디 임시저장소


## 프론트엔드 개발 패러다임의 변화
- 기존에는 CDN 방식을 사용 : `<script src=##.jquery.min.js></script>`
- 최근 패러다임은 Node.js 에서 제공하는 NPM 을 사용해서 라이브러리를 로컬에서 다운해 사용
    - 장점은 : 초기 SourceCode (스켈레톤 혹은 베어메탈) 는 많이 제공해주는 등등..
    - 단점은 : 대산 로컬에 설치된 버전에 따라 버전이 있을수도



## 용어정리
- SPA : 싱글페이지(하나의 HTML파일)에서 ㄱ
- 라우터 : 하나의 페이지에서 다른 주소의 페이지로 이동할때 주소창의 URL이 변경되고, 변경된 URL에 맞춰 WebApp이 다른 페이지를 제공해야하는데, 경로(페이지)이동시 해당하는 리소스를 제공하는 역할을 하는게 바로 라우터
- 



## 할일 (Todo List)

- 핵심만 빠르게 

### 백엔드레이어에서

- 스프링 웹소켓 : 실시간 업데이트 구현
- 스프링 AMQP : 비동기 백그라운드 작업
- 스프링 세션 : 세션관리



## 하지 말아야 할 일(Not Todo List)

- 일 크게벌려서 프로젝트 질질끄는거
- 자바스크립트에 시간 많이 퍼붓는거 (https://jsbin.com/) 적당히 최소한만



## 자바개발자 관점에서 자바스크립트와의 차이

### 함수와 메서드의 차이

- 자바스크립트에서 
  - 함수는 Function생성자로 생성된 객체이고
  - 메서드는 함수가 객체의 property일때, 함수가 다른객체에 완전히 종속적일때 메서드라고 칭함

### 동작의 차이

- 자바에서는 런타임에 메서드를 추가하거나 수정할수 있는 방법이 거의 없다(읽기는 Reflection API사용 )
- 새로운 프로퍼티를 추가하고 메서드를 교체하는게 런타임에 가능



### 스코프의 차이

- 자바의 스코프 : 변수의 접근성이 자바에서는 클래스레벨 / 메소드레벨 / 블록레벨(브레이스 내부)
- 자바스크립트의 스코프 : 전역스코프 / 함수 스코프 / 블록 스코프
  - ES6기준 {} 단위로 변수범위 제한이 걸림



### 호이스팅(Hoisting) 

- Hoisting 이란 선언한 함수와 변수를 해석기가 있는 상단에 있는 것 처럼 인식한다.

- js 해석기는 코드의 라인 순서와 관계 없이 함수 선언식과 변수를 위한 메모리 공간을 먼저 할당한다. JS 해석기가 함수란 함수는 그리고 변수는 죄다 다 위로 끌어올려서 메모리에 적재한다. JS 파일이 생각대로 순서대로 흘러가지 않는다

- function a()와 var는 코드의 최상단 으로 끌어 올려진 것(hoisted) 처럼 보인다.

- 코드

- ```
  function willBeOveridden() {
  return 10;
  }
  console.log(willBeOveridden()); //5 출력
  function willBeOveridden() {
  return 5;
  }
  console.log(willBeOveridden()); //5 출력됨
  ```



### const keyword 

- const로 지정한 값 변경 불가능하나
- 객체나 배열의 내부는 변경할 수 있다. 
- const 키워드가 원시타입에서는 상수이지만, 레퍼런스 타입에서는 재할당 금지의 의미를 갖는건 java나 js 나 동일한듯



### Arrow Function (람다표현식)

- 그냥 함수 때 function 키워드를 사용하지 않고 => 로 대체
- 콜백함수의 문법을 간결화, 함수의 바디부분만 남기고 나머지 추측할수 있는건 죄다 생략

```
var sum = (a, b) => {
	return a + b;
}

sum(10,20);
```

### 

```
var sum2 = (a,b) => a + b;
sum2(10,20);
```





### map, filter, reduce

```javascript
let arr = [10,20,30,40,50,60,70,80,90];
let result1 = arr.map(val => val+5);
/*


*/
console.log(result1);


//
//

let result2 = arr.map((val,idx) => val+idx);
console.log(result2);

let result3 = arr.filter(val => val%3 === 0);
console.log(result3)



///
//

let result4 = arr.reduce((prev,cur) => prev+cur);
console.log(result4);
```





## JS 코드 스니핏  몇가지



###  JS 람다에서 주의할부분 : this 키워드의 의미가 다르다(람다함수와 일반함수간)

```js
function Dog() {
  this.name = '백구';
  return {
    name:'황구',
    
    bark: function() {
      console.log(this.name + ' 멍멍!');
    },
    
    bark2: () => {
      console.log(this.name + ' 멍멍!');
    }
    
  }
}
const dog = new Dog();
dog.bark(); // 검둥이 멍멍!
dog.bark2(); // 검둥이 멍멍!

```



### Enhanced Object Literals (향상된 객체 리터럴)

- 객체의 속성을 메서드로 사용할 때 function 예약어를 생략

- ```js
  var dictionary {
  words: 100;
  
    //ES5 - 축약안함
  	lookup: function() {
  		console.log("find words");
  	},
    
  	//ES6
  	lookup() {
  		console.log("find words");
  	}
    
  }
  ```





###  The Ternary Operator (삼항 조건 연산자)





### Destructuring Assignment (비구조화 할당)

- swap : 값두개 변경

  - ```js
    let a = 1;
    let b = 3;
    [a, b] = [b, a];
    ```

- 분해

  - ```
    let obj = {p: 42, q: true};
    let {p, q} = obj;
    ```





### import와 export

- import / export 라는 방식으로 js모듈을 불러오고 내보낸다. 
- Export는 내부 스크립트 객체를 외부 스크립트로 모듈화함
- export 하지 않으면 외부 스크립트에서 import를 사용할 수 없다

- default 키워드가 붙어있으면 그냥 되는데
  - default 키워드가 안붙어있으면, 클래스로 한번 꼭 감싸줘야함

## 메시지로 전달







## 뷰가 랜더링 되는 순서

public/index.html<div id="app"></div>



- 웹팩의 config.js 에서 main.js 를 호출한다

src/main.js

new Vue({ render: h => h(App),}).$mount('#app')

src/App.vue<HelloWorld msg="Welcome to Your Vue.js App"/>

src/components/HelloWorld.vue

- 




## v-bind (중요)





## v-model(two-way-binding)의 응용
- checkbox를 만들어서 그 checkbox의 값에 따라서 다른 image를 보여준다.
- checkbox의 속성에 v-model="flag" 설정한다.

```html
</ul>
  Nmae: <input type="text" v-model="name"/>        
<ul>
```
- v-modle은 양방향




## MVVM 모델

- 문제점 : Javascript에서 컨트롤러 혹은 프리젠터 역할까지 하면서 코드의 분량이 증가하는 단점이 있었다 (ViewModel이 없는 아키텍처)
- ViewModel에 자바스크립트 객체와 DOM을 연결해 주면 ViewModel은 이 둘간의 동기화를 자동으로 처리한다.(re-Randering, 다시그리기)
- 이것이 Vuejs가 하는 역할이다. 즉, MVVM 모델의 VM을 Vue.js가 동기화처리를 담당, 양방향 동기화이기 때문에 modelview - viewmodel
  - modelview : HTML DOM이 View 역할
  - viewmodel : Javascript가 Model 역할
- 과거에 제이쿼리같은데서는 자바스크립트 코드로 엄청~ 많이 고생해서 해냈다

### 어떻게 양뱡향 동기화를 실현할까?? : VirtualDOM
- 한줄요약 : 기존에는 업데이트 되든말든 화면전체를 랜더링했는데 >> virtualDOM에다가 버퍼링을 해두고 바뀐 부분만 빠르게 슥삭 다시실제 DOM에다가 적용
- 동작
  1. 변화가 일어났다. 변화된 버전을 Virtual DOM으로 바꾸자 :: 데이터가 업데이트 되면 전체 UI를 가상돔에 Re렌더링한다.
  2. Virtual DOM 끼리 비교하자 :: 변화 전의 virtual dom 과 변화된 virtual dom 을 비교한다.
  3. 비교하여 바뀐 부분만 적용하자 :: 바뀐 부분만 실제 DOM에 적용을 함으로서 레이아웃 계산은 한 번만 이행된다


## MV 와 VM 이 데이터를 공유하는 

```
       [APP]
         |
  ---------------
  |             |
HW             MyDir 

```
- HW에서이벤트를 Emit(통지) 
- APP에서 받고
- APP에서 내려주고
- M