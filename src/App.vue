<template>
  <div id="app">
    <h1>Math Quiz App</h1>
    <OperatorQuiz  @onBack="clearOperator"  v-if="operator" :operator="operator" />
    <OperatorSelector v-if="!operator" @changeOperator="changeOperator" />
    
  </div>
</template>

<script>
import OperatorSelector from './components/OperatorSelector.vue'
import OperatorQuiz from './components/OperatorQuiz.vue'

export default {
  name: 'App',
  data(){
    return{
      operator: null,
    };
  },
  methods:{
    changeOperator(operator){
      this.operator=operator;
    },
    clearOperator(){
      this.operator = null
    }
  },
  components: {
   OperatorSelector,
   OperatorQuiz
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
  margin: 150px;
  font-size:24px;
box-sizing:flex;
}
button{
  padding:10px;
  width:160px;
  margin:10px;
  height:80px;
  vertical-align:top;
  background-color: #10aeb2;
  color:white;
  font-size:22px;
  cursor: pointer;

}
</style>
