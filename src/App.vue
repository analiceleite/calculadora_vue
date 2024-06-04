<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operator: '+',
      result: 0
    };
  },
  methods: {
    calculate() {
      switch (this.operator) {
        case '+':
          this.result = this.num1 + this.num2;
          break;
        case '-':
          this.result = this.num1 - this.num2;
          break;
        case '*':
          this.result = this.num1 * this.num2;
          break;
        case '/':
          this.result = this.num1 / this.num2;
          break;
      }
    }
  }
};
</script>

<template>
  <div class="container">
    <div class="row justify-content-center mt-5">
      <div class="col-md-6">
        <div class="card">
          <div class="card-body">
            <div class="form-group">
              <input type="number" class="form-control" v-model.number="num1" @input="calculate">
            </div>
            <div class="form-group mt-3">
              <select class="form-control" v-model="operator" @change="calculate">
                <option value="+">+</option>
                <option value="-">-</option>
                <option value="*">*</option>
                <option value="/">/</option>
              </select>
            </div>
            <div class="form-group mt-3">
              <input type="number" class="form-control" v-model.number="num2" @input="calculate">
            </div>
            <div class="form-group mt-3">
              <h4>Resultado: {{ result }}</h4>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card {
  border: none;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
}

.form-control {
  font-size: 16px;
}

h4 {
  font-size: 24px;
}
</style>
