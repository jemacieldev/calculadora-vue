<template>
  <div class="calculator-container">
    <div class="calculator">
      <h1>Calculadora Aritmética</h1>

      <div class="input-fields">
        <input
          type="number"
          v-model="number1"
          placeholder="Digite o primeiro número"
        />
        <select v-model="operation">
          <option value="add">+</option>
          <option value="subtract">-</option>
          <option value="multiply">*</option>
          <option value="divide">/</option>
        </select>
        <input
          type="number"
          v-model="number2"
          placeholder="Digite o segundo número"
        />
      </div>

      <div class="result">
        <h2>Resultado: {{ calculateResult }}</h2>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: 'add'
    };
  },
  computed: {
    calculateResult() {
      let result = 0;
      const num1 = parseFloat(this.number1);
      const num2 = parseFloat(this.number2);

      switch (this.operation) {
        case 'add':
          result = num1 + num2;
          break;
        case 'subtract':
          result = num1 - num2;
          break;
        case 'multiply':
          result = num1 * num2;
          break;
        case 'divide':
          result = num2 !== 0 ? num1 / num2 : 'Erro (divisão por 0)';
          break;
      }
      return result;
    }
  }
};
</script>

<style scoped>
.calculator-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: #f5f5dc; 
}

.calculator {
  border: 2px solid #ccc; 
  border-radius: 10px;
  padding: 30px;
  background-color: #fff;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  text-align: center;
}

.input-fields {
  margin-bottom: 20px;
}

input, select {
  margin: 10px;
  padding: 10px;
  font-size: 16px;
  border-radius: 5px;
  border: 1px solid #ccc;
}

.result h2, h1git init
{
  color: #333;
}
</style>

  