<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg-value="Welcome to Your Vue.js App" v-on:addEvent="addTodoList" />
    <hr/>
    <MyDiv title="my div title" :todos="todos"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import MyDiv from './components/MyDiv.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    MyDiv,
  },
  data() {
    return {
      todos: [
        { text: "Vue.js 튜토리얼 작성하기" },
        { text: "Webpack2 알아보기" },
        { text: "사이드 프로젝트 진행하기" },
      ],
    }
  },
  methods: {
    addTodoList(todo) {

      const todoObj = {text:todo};
      //todos 배열에 추가

      this.todoList.push(todoObj);
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
