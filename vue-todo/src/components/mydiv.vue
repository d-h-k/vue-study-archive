<template>
  <div>
    <h2>hello world! {{ title }}</h2>
    <ul>
      <li>상태변수 {{ name }}</li>
      <li>v-text속성 = <span v-text="name"></span></li>
      <li>
        v-html 속성 : html 형식을 읽어 랜더링합니다 =
        <span v-html="myhtml"></span>
      </li>
      <li>
        v-text속성 : 텍스트만 랜더링합니다 = <span v-text="myhtml"></span>
      </li>
      <li>
        v-show 속성 : 보일지 아닐지를 결정 =
        <span v-show="isShow" v-html="myhtml"></span>
      </li>
      <li>v-if속성 : <span v-if="value > 0" v-text="vifString"></span></li>
    </ul>
    <img v-bind:src="vuelogo" width="200" />
    <img :src="chita" width="200" />
    <!--- v-bind 생략 가능하다 이렇게 생략해둠 [:] --->

    <img :src="flag ? chita : anglogo" width="200" />
    <!--- 삼항연산자의 사용 --->



  <!--- 에러메시지 : [vue/require-v-for-key] : 여기 왜 안나오는지 모르겠습니다.. --->

    <ul>
      <li v-for="todo in todos" :key="todo.id">
        {{ todo.text }}
      </li>

      <!---  또다른 가능함 
        <li v-for="(todo,idx) in todos" :key="idx">
            
            {{todo}}
        </li>--->
    </ul>
    Nmae: <input type="text" v-model="name" />
    <ul>
      <h3><input type="checkbox" v-model="flag" />Logo 이미지</h3>
      <img :src="flag ? anglogo : vuelogo" width="200" />
    </ul>


    <div>
        Value = {{value}} <br>
        <button v-on:click="increment" 증가></button>
        <button @click="decrement" 감소></button>
        <!---  "v-on:" 을 압축&&생략해서 "@" 문자로 대체 가능 --->
    </div>


  </div>
</template>
<script>
export default {

  props: ["title","todos"], //부모(컴포넌트)로부터 물려받은 데이터들을 나타내는
  
  data() {
    //내 자신 내안의 컴포넌트에서 사용하는 변수
    return {
      name: `내부에서 쓰는 상태변수`,
      myhtml: "<i>VueJS</i>",
      isShow: false,
      value: 1,
      vifString: `0보다 크면 보이고, 작으면 안보임`,
      vuelogo: "https://vuejs.org/images/logo.png",
      chita:
        "https://w.namu.la/s/5fb1c943e0e910af237aed00dc23781cf177f421bebad7c0212d0d67f206f1bb6cbd4ba5427a7053095180ef783d4b60301e5a973b5bbd09e3213fb31715877cb4574d3a86565bc7a3d875e5104422ed7a6630c5e68932d6f50219505344df40",
      anglogo: "https://angular.io/assets/images/logos/angular/angular.svg",
      
      flag: true,
    };
  },
  methods: {
    increment () {
      //사용자 정의 함수, 이벤트 핸들러임
      this.value++;
    },
    decrement()  {
        this.value--;
    },
  }, //methods
}; // export
</script>
