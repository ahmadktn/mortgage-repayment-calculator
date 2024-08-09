<script setup>
import { ref } from 'vue';

import Calculator from './components/Calculator.vue';
import Result from './components/Result.vue';

const monthly = ref();
const total = ref();
const clicked = ref(false);
const errors = ref({
    amountError: false,
    termError: false,
    rateError: false,
    typeError: false,
  })

const getAmount = (amount, term, rate, type) => {
  if(!amount || !term || !rate || !type){
      console.warn('empty fields');
      if(!amount){
        errors.value.amountError = true;
      }
      else{
        errors.value.amountError = false;
      }

      if(!term){
        errors.value.termError = true;
      }
      else{
        errors.value.termError = false;
      }

      if(!rate){
        errors.value.rateError = true;
      }
      else{
        errors.value.rateError = false;
      }

      if(!type){
        errors.value.typeError = true;
      }
      else{
        errors.value.typeError = false;
      }
      return false;
    }else{ 
      errors.value.amountError = false;
      errors.value.termError = false;
      errors.value.rateError = false;
      errors.value.typeError = false;
      makeCalculations(amount, term, rate, type)
      return true;
    }
}

const makeCalculations = (amount, term, rate, type) => {
  if(type == 'repayment'){
    const r = rate/100;
    const n = 12;
    const years = 12*term;
    const numerator = amount*r/n;
    const denominator = 1-(1+r/n)**-years;
    const solution = (numerator / denominator);
    const new_m = Math.round(solution * 100) / 100;
    const new_t = new_m * years;
    monthly.value = Intl.NumberFormat('en-Us').format(new_m);
    total.value = Intl.NumberFormat('en-Us').format(new_t);
  }
  else if(type == 'interest-only'){
    const r = rate/100;
    const years = 12*term;
    const m = amount*r/12;
    const t = m*years;
    monthly.value = Intl.NumberFormat('en-Us').format(m);
    total.value = Intl.NumberFormat('en-Us').format(t);
  }
  if (amount > 1) {
    clicked.value = true;
  }
}

const clearForm = () => {
  errors.value.amountError = false;
  errors.value.termError = false;
  errors.value.rateError = false;
  errors.value.typeError = false;
  clicked.value = false;
}

</script>

<template>
  <div class="app-container">
    <Calculator @clear-form="clearForm" @submit="getAmount" :error-state="errors"/>
    <Result :monthly_payment="monthly" :total_payment="total" :is-clicked="clicked"/>
  </div>

</template>

<style scoped>

</style>
