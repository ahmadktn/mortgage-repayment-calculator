<script setup>

</script>

<template>
  <section class="wrapper">
    <div>
        <img src="../../assets/images/illustration-empty.svg">
    </div>
    <div class="info">
        <h2>Results shown here</h2>
        <p>
            Complete the form and click “calculate repayments” to see what 
your monthly repayments would be.
        </p>
    </div>
  </section>
</template>

<style scoped>
.wrapper{
    width: 100%;
    height: 100%;
    color: white;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 16px;
}
.info{
    text-align: center;
    color: white;
    display: flex;
    flex-direction: column;
    gap: 16px;
}
p{
    color: rgba(255, 255, 255, 0.7);
}
</style>