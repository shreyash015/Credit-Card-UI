<template>
  <div class="card-back-container">
    <img class="card-back" src="@/assets/bg-card-back.png" alt="">
    <div class="cvv-container">
      <p class="text-white">{{ cvv }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CardBack',
  props: {
    cvv : {
      type: String,
      default: '000'
    }
  },
}
</script>

<style scoped>

.card-back-container {
  margin-top: 30px;
  width: 400px;
  height: 223px;
  z-index: 999999;
  margin:0 auto;
  margin-top: 1rem;
  margin-bottom: 14rem;
}

.cvv-container {
  position: absolute;
  z-index: 9999999;
  top: 46%;
  right: 12%;
}

@media (min-width: 1024px) { 
  .card-back-container {
  margin-top: 30px;
  position: relative;
  /* top: 50%; */
  left: 50%;
  width: 425px;
  height: 223px;
  margin-bottom: 0rem;
  /* display: none; */
}

.cvv-container {
  position: absolute;
  z-index: 9999999;
  top: 46%;
  right: 12%;
}
}
</style>
