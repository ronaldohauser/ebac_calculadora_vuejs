<template>
  <div id="app">
    <div class="calculator">
      <div class="display">{{ resultado }}</div>
      <div class="input-container">
        <input v-model="num1" type="number" placeholder="Número 1" @input="calcular">
        <select v-model="operacao" @change="calcular">
          <option value="+">+</option>
          <option value="-">-</option>
          <option value="*">x</option>
          <option value="/">/</option>
        </select>
        <input v-model="num2" type="number" placeholder="Número 2" @input="calcular">
      </div>
      <div class="footer">
        &copy; 2023 Ronaldo H. Dias. <br>@ronaldohauser.
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operacao: '+',
      resultado: 0
    };
  },
  methods: {
    calcular() {
      switch (this.operacao) {
        case '+':
          this.resultado = this.num1 + this.num2;
          break;
        case '-':
          this.resultado = this.num1 - this.num2;
          break;
        case '*':
          this.resultado = this.num1 * this.num2;
          break;
        case '/':
          this.resultado = this.num1 / this.num2;
          break;
        default:
          this.resultado = 0;
      }
    }
  }
};
</script>

<style>
#app {
  font-family: 'Arial', sans-serif;
  text-align: center;
  margin-top: 60px;
}

.calculator {
  display: inline-block;
  background-color: #f0f0f0;
  border: 1px solid #ccc;
  border-radius: 10px;
  padding: 20px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.display {
  font-size: 40px;
  margin-bottom: 8px;
}

.input-container {
  display: flex;
  flex-direction: column;
}

input,
select {
  margin: 10px 0;
  padding: 15px;
  font-size: 18px;
  border: none;
  border-radius: 8px;
  background-color: #3498db; 
  color: #fff;
}

select {
  appearance: none;
  background-color: #3498db;
  padding: 16px;
  font-size: 18px;
}

input::placeholder {
  color: #ecf0f1;
}

.footer {
  margin-top: 8px;
  font-size: 12px;
  color: #777;
}
</style>
