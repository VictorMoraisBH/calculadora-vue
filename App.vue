<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>
    
    <div class="calculator">
      <input type="number" v-model.number="numero1" placeholder="Número 1" />
      <select v-model="operacao">
        <option value="add">+</option>
        <option value="sub">-</option>
        <option value="mul">*</option>
        <option value="div">/</option>
      </select>
      <input type="number" v-model.number="numero2" placeholder="Número 2" />

      <h2>Resultado: {{ resultado }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: "add"
    };
  },
  computed: {
    resultado() {
      switch (this.operacao) {
        case "add":
          return this.numero1 + this.numero2;
        case "sub":
          return this.numero1 - this.numero2;
        case "mul":
          return this.numero1 * this.numero2;
        case "div":
          return this.numero2 !== 0 ? this.numero1 / this.numero2 : 'Erro: Divisão por zero';
        default:
          return 0;
      }
    }
  }
};
</script>

<style scoped>
.calculator {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  margin-top: 20px;
}

input {
  width: 80px;
  padding: 5px;
  font-size: 16px;
}

select {
  padding: 5px;
  font-size: 16px;
}

h2 {
  margin-left: 20px;
}
</style>
