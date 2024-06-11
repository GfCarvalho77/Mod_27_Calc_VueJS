
<script>
import campoDeInsercao from './components/campoDeInsercao.vue';
import seletorDeOperacao from './components/seletorDeOperacao.vue';
import campoDeREsultado from './components/campoDeREsultado.vue';

export default {
  components: {
    campoDeInsercao,
    seletorDeOperacao,
    campoDeREsultado
  },
  data() {
    return {
      num1: 0,
      num2: 0,
      operation: 'add',
      result: 0
    };
  },
  watch: {
    num1() {
      this.calculaResultado();
    },
    num2() {
      this.calculaResultado();
    },
    operation() {
      this.calculaResultado();
    }
  },
  methods: {
    calculaResultado() {
      switch (this.operation) {
        case 'add':
          this.result = this.num1 + this.num2;
          break;
        case 'subtract':
          this.result = this.num1 - this.num2;
          break;
        case 'multiply':
          this.result = this.num1 * this.num2;
          break;
        case 'divide':
          this.result = this.num2 !== 0 ? this.num1 / this.num2 : 'Erro: Divisão por zero';
          break;
      }
    }
  },
  mounted() {
    this.calculaResultado();
  }
}
</script>

<template>
  <div id="app">
    <h1>Calculadora VueJS</h1>
    <campoDeInsercao 
      :num1="num1" 
      :num2="num2" 
      @update:num1="num1 = $event" 
      @update:num2="num2 = $event" 
    />
    <seletorDeOperacao 
      :operation="operation" 
      @update:operation="operation = $event" 
    />
    <campoDeREsultado :result="result" />
  </div>
</template>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #f30a0a;
  margin-top: 200px;
}
</style>





<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #ffffff;
  margin-top: 60px;
}
</style>