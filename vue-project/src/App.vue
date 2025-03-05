<template>
  <div id="app">
  <h1>Calculadora Aritmética</h1>
  <div class="calculator">
      <input type="number" v-model="numero1" placeholder="Digite o primeiro número" />
      <select v-model="operacao">
      <option value="/">/</option>
      </select>
      <input type="number" v-model="numero2" placeholder="Digite o segundo número" />
      <div class="resultado">
      <h2>Resultado: {{ resultado }}</h2>
      </div>
</div>
  </div>
</template>

<script>
export default {
  data() {
return {
      numero1: 0,
      numero2: 0,
      operacao: '+',
  };
  },
  computed: {
  resultado() {
      let res = 0;
      switch (this.operacao) {
      case '+':
          res = parseFloat(this.numero1) + parseFloat(this.numero2);
          break;
      case '-':
          res = parseFloat(this.numero1) - parseFloat(this.numero2);
          break;
      case '*':
          res = parseFloat(this.numero1) * parseFloat(this.numero2);
          break;
      case '/':
          if (parseFloat(this.numero2) !== 0) {
          res = parseFloat(this.numero1) / parseFloat(this.numero2);
          } else {
          res = 'Erro: Divisão por zero';
          }
          break;
      default:
          res = 0;
      }
      return res;
  },
  },
};
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  text-align: center;
  padding: 20px;
}

.calculator {
  display: flex;
  flex-direction: column;
  align-items: center;
}

input, select {
  margin: 10px;
  padding: 10px;
  font-size: 16px;
}

.resultado {
  margin-top: 20px;
  font-size: 24px;
  font-weight: bold;
}
</style>
