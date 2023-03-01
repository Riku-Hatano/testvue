<template>
  <div>
    <First-compo :person="person"/>
    <hr>
    <h1>{{person.fname}}</h1>
    <input v-model="person.fname">
    <input v-model="person.lname">
    <hr>
    <Button-compo :person="person"/>
    <hr>
    <input v-model="num1">
    <input v-model="num2">
    <button @click="getOperate">+</button>
    <button @click="getOperate">-</button>
    <button @click="getOperate">*</button>
    <button @click="getOperate">/</button>
    <Cal-Result-compo :num1="num1" :num2="num2" :operate="operate" :result="result"/>
  </div>
</template>

<script>
import ButtonCompo from './components/ButtonCompo.vue';
import CalResultCompo from './components/CalResultCompo.vue';
import FirstCompo from './components/firstCompo.vue';
import stuData from "./json/stu.json";

export default {
  name: 'App',
  components: {
    FirstCompo,
    ButtonCompo,
    CalResultCompo
  },
  data() {
    return {
      stuData: stuData,
      fname: "",
      lname: "",
      person: {
        fname: "",
        lname: ""
      },
      num1: 0,
      num2: 0,
      result: 0,
      operator: "",
    }
  },
  methods: {
    welcome() {
      this.person = {fname:this.fname, lname:this.lname}
    },
    getOperate(e) {
      console.log(JSON.parse(JSON.stringify(this.stuData)))
      this.operate = e.target.innerHTML
      switch(e.target.innerHTML) {
        case "+":
          this.result = parseInt(this.num1) + parseInt(this.num2);
          break;
        case "-":
          this.result = this.num1 - this.num2;
          break;
        case "*":
          this.result = this.num1 * this.num2;
          break;
        case "/":
          this.result = this.num1 / this.num2;
          break;
      }
    }
  }
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
