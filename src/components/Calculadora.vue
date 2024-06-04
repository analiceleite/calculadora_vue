<template>
  <div class="container">
    <div class="row justify-content-center mt-5">
      <div class="col-md-6">
        <div class="card">
          <div class="card-body">
            <div class="form-group">
              <input
                type="number"
                class="form-control"
                :value="num1"
                @input="$emit('update:num1', Number($event.target.value))"
              />
            </div>
            <div class="form-group mt-3">
              <select
                class="form-control"
                :value="operator"
                @change="$emit('update:operator', $event.target.value)"
              >
                <option value="+">+</option>
                <option value="-">-</option>
                <option value="*">*</option>
                <option value="/">/</option>
              </select>
            </div>
            <div class="form-group mt-3">
              <input
                type="number"
                class="form-control"
                :value="num2"
                @input="$emit('update:num2', Number($event.target.value))"
              />
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

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  num1: Number,
  num2: Number,
  operator: String,
  result: Number,
  calculate: Function,
});
</script>

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
