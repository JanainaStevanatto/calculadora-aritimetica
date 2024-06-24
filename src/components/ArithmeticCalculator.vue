<template>
  <div class="ArithmeticCalculator">
    <h1>Calculadora Aritmética</h1>
    <div class="input-fields">
      <input type="number" v-model.number="number1" @input="calculate" placeholder="Primeiro número" />
      <select v-model="operation" @change="calculate">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>
      <input type="number" v-model.number="number2" @input="calculate" placeholder="Segundo número" />
    </div>
    <div class="result">
      <h2>Resultado: {{ result }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ArithmeticCalculator',
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: '+',
      result: 0
    };
  },
  methods: {
    calculate() {
      switch (this.operation) {
        case '+':
          this.result = this.number1 + this.number2;
          break;
        case '-':
          this.result = this.number1 - this.number2;
          break;
        case '*':
          this.result = this.number1 * this.number2;
          break;
        case '/':
          this.result = this.number2 !== 0 ? this.number1 / this.number2 : 'Erro: Divisão por zero';
          break;
      }
    }
  },
  mounted() {
    this.calculate();
  }
};
</script>

<style scoped>
.ArithmeticCalculator {
  max-width: 400px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 8px;
  text-align: center;
}
.input-fields {
  display: flex;
  justify-content: space-between;
  margin-bottom: 20px;
}
input,
select {
  width: 30%;
  padding: 8px;
  font-size: 1em;
}
.result {
  font-size: 1.5em;
  font-weight: bold;
}
</style>
