<script setup>
import { ExclamationCircleIcon } from '@heroicons/vue/20/solid'
</script>
<template>
  <div class="lg:h-screen">
    <div class="lg:flex lg:flex-col lg:grid lg:grid-cols-9 grid">
      <div class="left-bg max-h-full lg:h-screen lg:col-span-2 relative">
        <div class="card-container relative">
          <CardFront :cardholderName="cardholderName" :cardNumber="cardNumber" :cardMonth="cardMonth" :cardYear="cardYear"></CardFront>
          <CardBack :cvv="cvv"></CardBack>
        </div>
      </div>
      <div class="lg:h-screen lg:col-span-7 right-container bg-gray-100">
        <div v-if="!confirmClicked" class="py-8 form-container h-full flex items-center justify-center">
          <div class="md:w-96 w-64">
            <label for="name" class="block text-sm font-medium leading-6 uppercase  text-gray-900">Cardholder
              Name</label>
            <div class="relative mt-1 rounded-md shadow-sm">
              <input type="text" name="name" id="name" v-model="cardholderName"
                maxlength="16"
                class="block w-full rounded-md border-0 py-1.5 pr-10 text-gray-900 ring-1 ring-inset ring-gray-300 placeholder:text-gray-300 focus:ring-2 focus:ring-inset focus:ring-gray-500 sm:text-sm sm:leading-6"
                placeholder="e.g. Jane Appleseed" aria-invalid="true" aria-describedby="name-error" />
              <div class="pointer-events-none absolute inset-y-0 right-0 flex items-center pr-3">
                <!-- <ExclamationCircleIcon class="h-5 w-5 text-gray-500" aria-hidden="true" /> -->
              </div>
            </div>
            <!-- <p class="mt-2 text-xs text-gray-600" id="email-error">Not a valid card number.</p> -->

            <label for="card-number" class="mt-4 block text-sm font-medium leading-6 uppercase  text-gray-900">Card
              Number</label>
            <div class="relative mt-1 rounded-md shadow-sm">
              <input type="string" name="card-number" id="card-number" v-model="cardNumber"
                maxlength="16"
                minlength="16"
                class="block w-full rounded-md border-0 py-1.5 pr-10 pl-2 text-gray-900 ring-1 ring-inset ring-gray-300 placeholder:text-gray-300 focus:ring-2 focus:ring-inset focus:ring-gray-500 sm:text-sm sm:leading-6"
                placeholder="e.g. 1234 5678 9123 0000" aria-invalid="true" aria-describedby="card-number-error" />
              <div class="pointer-events-none absolute inset-y-0 right-0 flex items-center pr-3">
                <!-- <ExclamationCircleIcon class="h-5 w-5 text-gray-500" aria-hidden="true" /> -->
              </div>
            </div>
            <!-- <p class="mt-2 text-sm text-gray-600" id="email-error">Not a valid email address.</p> -->


            <div class="relative mt-1 rounded-md shadow-sm md:grid md:grid-cols-5 md:gap-x-3">
              <div class="md:col-span-2">
                <label for="month" class="mt-4 block text-sm font-medium leading-6 uppercase  text-gray-900">Exp.
                  Date (MM/YY)</label>
                <div class="grid grid-cols-2 gap-x-2">
                  <div class="">
                    <input type="string" name="month" id="month" v-model="cardMonth"
                      maxlength="2"
                      class="block w-full rounded-md border-0 py-1.5 pr-8 pl-2 text-gray-900 ring-1 ring-inset ring-gray-300 placeholder:text-gray-300 focus:ring-2 focus:ring-inset focus:ring-gray-500 sm:text-sm sm:leading-6"
                      placeholder="MM" aria-invalid="true" aria-describedby="month-error" />
                  </div>
                  <div class="">
                    <input type="string" maxlength="2" name="year" id="year" v-model="cardYear"
                      class="block w-full rounded-md border-0 py-1.5 pr-8 pl-2 text-gray-900 ring-1 ring-inset ring-gray-300 placeholder:text-gray-300 focus:ring-2 focus:ring-inset focus:ring-gray-500 sm:text-sm sm:leading-6"
                      placeholder="YY" aria-invalid="true" aria-describedby="year-error" />
                  </div>
                </div>
              </div>

              <div class="md:col-span-3">
                <label for="cvc" class="mt-4 block text-sm font-medium leading-6 uppercase  text-gray-900">CVC</label>
                <input type="string" maxlength="3" name="cvc" id="cvc" v-model="cvv"
                  class="block w-full rounded-md border-0 py-1.5 pr-8 pl-2 text-gray-900 ring-1 ring-inset ring-gray-300 placeholder:text-gray-300 focus:ring-2 focus:ring-inset focus:ring-gray-500 sm:text-sm sm:leading-6"
                  placeholder="e.g. 123" aria-invalid="true" aria-describedby="cvc-error" />
              </div>
            </div>
            <!-- <p class="mt-2 text-sm text-gray-600" id="email-error">Not a valid email address.</p> -->

            <a href="#"
            @click="confirmClicked = true"
              class="border bg-stone-700 text-white w-full flex items-center justify-center mt-8 py-2.5 rounded-md">Confirm</a>
          </div>
        </div>
        <div v-else class="form-container h-full flex items-center justify-center">
          <div class="w-96">
            <p class="block text-2xl text-center tracking-widest font-medium leading-6 uppercase  text-gray-900">Thank You!</p>
            <p class="block text-xs mt-4 text-center tracking-widest font-medium leading-6 uppercase  text-gray-500">We've added your card details</p>



            <a href="#"
              class="border bg-stone-700 text-white w-full flex items-center justify-center mt-8 py-2.5 rounded-md">Continue</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import CardFront from '@/components/CardFront.vue';
  import CardBack from '@/components/CardBack.vue';
  
  export default {
  data() {
    return {
      cardholderName: '',
      cardNumber: '',
      cardMonth: '',
      cardYear: '',
      cvv: '',
      confirmClicked: false
    }
  },
}
</script>

<style scoped>
.left-bg {
  background: url(@/assets/bg-main-desktop.png);
  background-size: cover;
}

.card-container{
  top: 25%;
}
</style>
