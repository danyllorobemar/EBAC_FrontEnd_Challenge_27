<script>
export default {
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: '+',
    };
  },
  computed: {
    result() {
      switch (this.operation) {
        case '+':
          return this.number1 + this.number2;
        case '-':
          return this.number1 - this.number2;
        case '*':
          return this.number1 * this.number2;
        case '/':
          return this.number2 !== 0 ? this.number1 / this.number2 : 'Erro: Divisão por zero';
        default:
          return 0;
      }
    },
  },
};
</script>

<template>
  <div id="app" class="container mt-5">
    <h1 class="text-center text-primary mb-4">Calculadora Aritmética</h1>
    <div class="card card-custom mx-auto p-4">
      <div class="mb-3">
        <label for="number1" class="form-label">Número 1</label>
        <input type="number" v-model.number="number1" id="number1" class="form-control" placeholder="Número 1" />
      </div>
      <div class="mb-3">
        <label for="operation" class="form-label">Operação</label>
        <select v-model="operation" id="operation" class="form-select">
          <option value="+">+</option>
          <option value="-">-</option>
          <option value="*">*</option>
          <option value="/">/</option>
        </select>
      </div>
      <div class="mb-3">
        <label for="number2" class="form-label">Número 2</label>
        <input type="number" v-model.number="number2" id="number2" class="form-control" placeholder="Número 2" />
      </div>
      <div class="text-center">
        <p class="fs-4 fw-bold">Resultado: {{ result }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
#app {
  text-align: center;
}

.card-custom {
  max-width: 400px;
}

#number1 {
  text-align: center;
}
</style>