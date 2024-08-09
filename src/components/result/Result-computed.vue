<script setup>
defineProps ({
  payment: {
    type: String
  },
  total: {
    type: String
  }
})
</script>

<template>
  <section class="wrapper">
    <div class="info">
        <h2>Your results</h2>
        <p>
          Your results are shown below based on the information you provided. 
  To adjust the results, edit the form and click “calculate repayments” again.
        </p>
    </div>
    <div class="card">
      <div class="top">
        <p>Your monthly repayments</p>
        <h1>&euro;{{ payment }}</h1>
      </div>
      <div class="line">
        <hr>
      </div>
      <div class="bottom">
        <p>Total you'll repay over the term</p>
        <h2>&euro;{{ total }}</h2>
      </div>
    </div>
  </section>
</template>

<style scoped>
.wrapper{
    width: 100%;
    height: fit-content;
    color: white;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 16px;
}
p{
  color: hsla(0, 0%, 100%, 0.7);
}
.info{
    text-align: left;
    color: white;
    display: flex;
    flex-direction: column;
    gap: 16px;
}
.card{
  width: 100%;
  padding: 20px;
  box-sizing: border-box;
  background-color: hsl(201, 53%, 12%);
  border-top: 3px solid hsl(61, 70%, 52%);
  border-radius: 12px;
  display: flex;
  flex-direction: column;
  gap: 12px;
  margin-top: 20px;
}
.card p{
  margin-bottom: 8px;
}
.top h1{
  font-size: 2rem;
  color: hsl(61, 70%, 52%);
}
.line hr{
  color: hsla(0, 0%, 100%, 0.5);
}

@media (width >= 800px){
  .card{
    gap: 28px;
  }
  .top h1{
    font-size: 3rem;
  }
}
</style>