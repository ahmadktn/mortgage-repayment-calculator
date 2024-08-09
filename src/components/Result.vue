<script setup>
import { ref } from 'vue';

import ResultEmpty from './result/Result-empty.vue';
import ResultComputed from './result/Result-computed.vue';

defineProps ({
  monthly_payment: {
    type: String
  },
  total_payment: {
    type: String
  },
  isClicked: {
    type: Boolean
  }
})

</script>

<template>
  <main class="container">

    <ResultComputed :payment="monthly_payment" :total="total_payment" v-if="isClicked" />
    <ResultEmpty v-else-if="!isClicked" />
    
  </main>
</template>

<style scoped>
.container{
  background-color: hsl(202, 55%, 16%);
}

@media (width >= 800px){
  .container{
    width: 50%;
    border-radius: 0 20px 20px 80px;
  }
}
</style>