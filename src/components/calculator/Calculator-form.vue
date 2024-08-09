<script setup>
import { ref } from 'vue';

const amount = ref('');
const term = ref('');
const rate = ref('');
const type = ref('');

// const send = () => {
  
// }

</script>

<template>
  <section>
    <form class="form-container">
      <div class="input-container">
      
        <label for="amount" class="label">Mortgage Amount</label>
        <div class="input-item">
          <span>&euro;</span>
          <input type="number" id="amount" v-model="amount">
        </div>
      </div>

      <div class="input-container row">
        <div>
          <label for="term" class="label">Mortgage Term</label>
          <div class="input-item mortgage">
            <input type="number" id="term" v-model="term">
            <span>years</span>
          </div>
        </div>

        <div>
            <label for="rate" class="label">Interest Rate</label>
            <div class="input-item">
              <input type="number" id="rate" v-model="rate">
              <span>%</span>
            </div>
        </div>
      </div>

      <div class="input-container">
        <p class="label">Mortgage Type</p>
        <div class="input-radio">
          <input type="radio" id="repayment" value="repayment" v-model="type">
          <label for="repayment">Repayment</label>
        </div>
        <div class="input-radio">
          <input type="radio" id="interest-only" value="interest-only" v-model="type">
          <label for="interest-only">Interest Only</label>
        </div>
      </div>

      <div>
        <button class="submit-btn" @click.prevent="$emit('calculate', amount, term, rate, type);
  amount = '';
  term =  '';
  rate = '';
  type = '';"><img src="../../assets/images/icon-calculator.svg">Calculate Repayment</button>
      </div>
        

    </form>
  </section>
</template>

<style scoped>
.form-container{
  display: flex;
  flex-direction: column;
  gap: 20px;
}
.input-container label{
  color: hsl(202, 55%, 16%);
}
.input-item{
  border: 2px solid hsl(200, 24%, 40%);
  border-radius: 8px;
  display: flex;
  overflow: hidden;
  cursor: pointer;
}
.input-item span{
  width: 10%;
  background-color: hsl(203, 41%, 72%);
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
  border: none;
  outline: none;
  cursor: pointer;
  appearance: textfield;
}
.input-radio{
  display: flex;
  padding: 1rem;
  border: 2px solid hsl(200, 24%, 40%);
  gap: 16px;
  border-radius: 8px;
  margin-bottom: 12px;
  cursor: pointer;
}
.input-radio label{
  cursor: pointer;
}
.submit-btn{
  width: 100%;
  padding: 1rem;
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
  border: 2px solid black;
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
  margin-bottom: 20px;
}

@media (width >= 800px){
  .row{
    flex-direction: row;
  }
  .input-item span{
    width: 20%;
  }
  .mortgage span{
  width: 30%;
  }
  .mortgage input{
    width: 70%;
  }
}
</style>