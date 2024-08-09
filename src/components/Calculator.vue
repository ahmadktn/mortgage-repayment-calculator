<script setup>
import { ref } from 'vue';

defineProps({
  errorState: Object
})

const amount = ref();
const term = ref();
const rate = ref();
const type = ref();
</script>

<template>
  <main class="container">
    <div class="calculator-header">
      <h2>Mortgage Calculator</h2>

      <button class="clear-btn" @click.prevent="$emit('clear-form'); amount = ''; term = ''; rate = ''; type= '';">Clear all</button>
    </div>
    
    <section>
    <form class="form-container">
      <div class="input-container">
      
        <p for="amount" class="label">Mortgage Amount</p>
        <div :class="{'input-item': true, 'error-item': errorState.amountError}">
          <span :class="{'error-state': errorState.amountError}">&euro;</span>
          <input name="amount" type="number" id="amount" v-model="amount" />
        </div>
        <p style="margin-top: 12px;" :class="{'notactive': !errorState.amountError, 'error-message': errorState.amountError}">Input required</p>
      </div>

      <div class="input-container row">
        <div>
          <p for="term" class="label">Mortgage Term</p>
          <div :class="{'input-item mortgage': true, 'error-item': errorState.termError}">
            <input name="term" type="number" id="term" v-model="term" />
            <span :class="{'error-state': errorState.termError}">years</span>
          </div>
          <p style="margin-top: 12px;" :class="{'notactive': !errorState.termError, 'error-message': errorState.termError}">Input required</p>
        </div>

        <div>
            <p for="rate" class="label">Interest Rate</p>
            <div :class="{'input-item': true, 'error-item': errorState.rateError}">
              <input name="rate" type="number" id="rate" v-model="rate" />
              <span :class="{'error-state': errorState.rateError}">%</span>
            </div>
            <p style="margin-top: 12px;" :class="{'notactive': !errorState.rateError, 'error-message': errorState.rateError}">Input required</p>
        </div>
      </div>

      <div class="input-container">
        <p class="label">Mortgage Type</p>
        <div class="input-radio">
          <input name="type" type="radio" id="repayment" value="repayment" v-model="type" />
          <label for="repayment">Repayment</label>
        </div>
        <div class="input-radio">
          <input name="type" type="radio" id="interest-only" value="interest-only" v-model="type" />
          <label for="interest-only">Interest Only</label>
        </div>
        <p :class="{'notactive': !errorState.typeError, 'error-message': errorState.typeError}">Input required</p>
      </div>

      <div>
        <button class="submit-btn" @click.prevent="$emit('submit', amount, term, rate, type)"><img src="../assets/images/icon-calculator.svg">Calculate Repayment</button>
      </div>
        

    </form>
  </section>

    
  </main>
  
</template>

<style scoped>
.calculator-header{
  display: flex;
  flex-direction: column;
  justify-content: start;
  align-items: start;
  margin-bottom: 24px;
}
h2{
  color:hsl(202, 55%, 16%);
}
.clear-btn{
  border: none;
  outline: none;
  background-color: transparent;
  text-decoration: underline;
  cursor: pointer;
  color: hsl(200, 24%, 40%);
}

.form-container{
  display: flex;
  flex-direction: column;
  gap: 20px;
}
.input-container label{
  color: hsl(200, 26%, 54%);
}
.input-item{
  border: 2px solid hsl(203, 41%, 72%);
  border-radius: 8px;
  display: flex;
  overflow: hidden;
  cursor: pointer;
}
.input-item span{
  width: 10%;
  background-color: hsl(202, 86%, 94%);
  text-align: center;
  vertical-align: middle;
  justify-content: center;
  align-items: center;
  display: flex;
}
.mortgage span{
  width: 20%;
}
.mortgage input{
  width: 80%;
}
.input-item input{
  padding: 1rem;
  width: 90%;
  color: hsl(202, 55%, 16%);
  font-family: Plus-bold;
  font-size: 16px;
  font-weight: 700;
  border: none;
  outline: none;
  cursor: pointer;
  appearance: textfield;
}
.input-radio{
  display: flex;
  padding: 1rem;
  border: 2px solid hsl(203, 41%, 72%);
  gap: 16px;
  border-radius: 8px;
  margin-bottom: 12px;
  cursor: pointer;
}
.input-radio label{
  cursor: pointer;
  font-weight: 700;
  color: hsl(202, 55%, 16%);
}
.submit-btn{
  width: 100%;
  padding: 1rem;
  font-size: 16px;
  font-family: Plus-bold;
  background-color: hsl(61, 70%, 52%);
  border: none;
  outline: none;
  border-radius: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 12px;
  font-weight: bold;
  cursor: pointer;
}
.input-item:hover{
  border: 2px solid hsl(202, 55%, 16%);
}
.input-radio:hover{
  border: 2px solid hsla(61, 70%, 52%, 0.7);
}
.submit-btn:hover{
  background-color: hsla(61, 70%, 52%, 0.7);
}
.row{
  display: flex;
  flex-direction: column;
  gap: 20px;
}
.label{
  margin-bottom: 12px;
  color: hsl(200, 24%, 40%);
}


@media (width >= 800px){
  .calculator-header{
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
  }
  .container{
    width: 50%;
  }
  .row{
    flex-direction: row;
  }
  .input-item span{
    width: 20%;
  }
  .mortgage span{
  width: 30%;
  }
  .mortgage input, .submit-btn{
    width: 70%;
  }

}

.notactive{
  display: none;
}
.error-message{
  display: block;
  font-size: 12px;
  color: hsl(4, 69%, 50%);
}
.error-item{
  border: 2px solid hsl(4, 69%, 50%);
}
.error-item .error-state{
  background-color: hsl(4, 69%, 50%);
  color: white
}
</style>

