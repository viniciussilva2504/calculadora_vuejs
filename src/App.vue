<template>
  <div class="calculator">
    <h1>Calculadora Aritmética</h1>
    
    <div>
      <label>Número 1:</label>
      <input type="number" v-model.number="num1" />
    </div>

    <div>
      <label>Número 2:</label>
      <input type="number" v-model.number="num2" />
    </div>

    <div>
      <label>Operação:</label>
      <select v-model="operacao">
        <option value="+">Soma (+)</option>
        <option value="-">Subtração (-)</option>
        <option value="*">Multiplicação (*)</option>
        <option value="/">Divisão (/)</option>
      </select>
    </div>

    <div>
      <h2>Resultado: {{ resultado }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operacao: '+'
    }
  },
  computed: {
    resultado() {
      switch (this.operacao) {
        case '+': return this.num1 + this.num2
        case '-': return this.num1 - this.num2
        case '*': return this.num1 * this.num2
        case '/': return this.num2 !== 0 ? (this.num1 / this.num2) : 'Erro: divisão por zero'
        default: return 'Operação inválida'
      }
    }
  }
}
</script>

<style scoped>
.calculator {
  max-width: 400px;
  margin: 40px auto;
  padding: 30px;
  border-radius: 20px;
  background: linear-gradient(145deg, #f0f8ff, #cfe0f1);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  color: #333;
  text-align: center;
}

h1 {
  margin-bottom: 20px;
  color: #005bac;
  font-size: 1.8rem;
}

label {
  font-weight: bold;
  color: #004080;
  display: block;
  text-align: left;
  margin-bottom: 5px;
}

input,
select {
  display: block;
  width: 100%;
  padding: 12px;
  margin: 10px 0 20px 0;
  border: none;
  border-radius: 10px;
  background-color: #e6f2ff;
  font-size: 16px;
  box-shadow: inset 2px 2px 5px #b0c4de, inset -2px -2px 5px #ffffff;
  transition: background-color 0.3s ease;
}

input:focus,
select:focus {
  background-color: #d0e7ff;
  outline: none;
}

h2 {
  margin-top: 20px;
  font-size: 24px;
  color: #008080;
  background-color: #e0ffff;
  padding: 15px;
  border-radius: 10px;
  box-shadow: 0 0 8px #add8e6;
}

/* 🔻 Responsividade para telas pequenas */
@media (max-width: 480px) {
  .calculator {
    margin: 20px 10px;
    padding: 20px;
    border-radius: 15px;
  }

  h1 {
    font-size: 1.5rem;
  }

  input,
  select {
    font-size: 14px;
    padding: 10px;
  }

  h2 {
    font-size: 20px;
    padding: 12px;
  }
}
</style>


