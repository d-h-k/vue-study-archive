<template>
  <div class="hello">
    <h1>{{ msgValue }}</h1>

    Name : <input type="text" v-model="todo" />
    <button @click="addTodo">    추가</button>

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: ["msgValue"],
  data() {
    return {
      todo: '',
    }
  },
  methods: {
    addTodo() {
      // Click 이벤트가 발생했음을 APP의 부모컴포넌트에 통지하기(알려주기)


      //this.$emit("addEvent", this.todo); // 이벤트의 이름은 addEvent, 콜백함수는 
        console.log("test todo func called");

    },

  },
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
