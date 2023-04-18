<template>
  <div class="card-front-container">
    <img class="card-front" src="@/assets/bg-card-front.png" alt="">
    <div class="inner-card-details md:flex md:flex-col md:justify-between">
      <div class="lg:px-4">
        <img class="card-logo" src="@/assets/card-logo.svg" alt="">
      </div>
      <div class="card-details-container text-white text-2xl tracking-widest  w-full lg:px-4 py-4">
        <div class="flex justify-between">
          <div class="inline-block"> {{ (cardNumber.split("").slice(0, 4).join("")) || "0000" }}</div>
          <div class="inline-block"> {{ cardNumber.split("").slice(4, 8).join("") || "0000" }}</div>
          <div class="inline-block"> {{ cardNumber.split("").slice(8, 12).join("") || "0000" }}</div>
          <div class="inline-block"> {{ cardNumber.split("").slice(12, 16).join("") || "0000" }}</div>
        </div>
        <div class="flex text-base justify-between mt-4 2xl:px-4">
          <p class="uppercase">{{ cardholderName || 'Jane Appleseed' }}</p>
          <p>{{ cardMonth || "00" }}/{{ cardYear || "00" }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CardFront',
  props: {
    cardholderName: {
      type: String,
      default: 'Jane Appleseed'
    },
    cardNumber: {
      type: String,
      default: '0000 00000 0000 000'
    },
    cardMonth: {
      type: String,
      default: '00'
    },
    cardYear: {
      type: String,
      default: '00'
    }
  },
  data() {
    return {

    }
  },
}
</script>

<style scoped>

.card-front-container {
  position: relative;
  /* top: 20%; */
  width: 400px;
  height: 223px;
  margin: 0 auto;
}

.inner-card-details {
  position: absolute;
  top: 5%;
  /* left: 30%; */
  height: 95%;
  width: 100%;
  padding: 0 1rem;
}

.card-logo {
  z-index: 9999999;
  position: inherit;
}


.card-details-container {
  /* position: absolute; */
  z-index: 99999;
  /* top: 60%; */
  /* left: 100%; */
}


.card-front {
  position: relative;
  /* top: 20%; */
  /* left: 30%; */
  width: 100%;

}

@media (min-width: 1024px) { 
  .card-front-container {
  position: relative;
  /* top: 20%; */
  width: 425px;
  height: 223px;
}

.inner-card-details {
  position: absolute;
  top: 5%;
  left: 30%;
  height: 95%;
  width: 100%;
}

.card-logo {
  z-index: 9999999;
  position: inherit;
}


.card-details-container {
  /* position: absolute; */
  z-index: 99999;
  /* top: 60%; */
  /* left: 100%; */
}


.card-front {
  position: relative;
  /* top: 20%; */
  left: 30%;
  width: 100%;

}
 }
</style>
