<script setup>
import HelloWorld from './components/HelloWorld.vue'
</script>
<template>
  <div class="md:h-screen">
    <div class="md:grid md:grid-cols-9">
      <div class="left-bg md:h-screen md:col-span-2 relative">
        <img class="card-front" src="@/assets/bg-card-front.png" alt="">
        <img class="card-back" src="@/assets/bg-card-back.png" alt="">
      </div>
      <div class="md:h-screen md:col-span-7 right-container bg-gray-100 border border-red-500">
        <div class="form-container flex items-center justify-center">
            <div class="flex flex-1 flex-col justify-center px-4 py-12 sm:px-6 lg:flex-none lg:px-20 xl:px-24">
              <div class="mx-auto w-full max-w-sm lg:w-96">
                <div class="mt-8">
                  <div class="mt-6">
                    <form action="#" method="POST" class="space-y-6">
                      <div>
                        <label for="email" class="block text-sm font-medium leading-6 text-gray-900">Email address</label>
                        <div class="mt-2">
                          <input id="email" name="email" type="email" autocomplete="email" required
                            class="block w-full rounded-md border-0 py-1.5 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6">
                        </div>
                      </div>

                      <div class="space-y-1">
                        <label for="password" class="block text-sm font-medium leading-6 text-gray-900">Password</label>
                        <div class="mt-2">
                          <input id="password" name="password" type="password" autocomplete="current-password" required
                            class="block w-full rounded-md border-0 py-1.5 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6">
                        </div>
                      </div>

                      <div class="flex items-center justify-between">
                        <div class="flex items-center">
                          <input id="remember-me" name="remember-me" type="checkbox"
                            class="h-4 w-4 rounded border-gray-300 text-indigo-600 focus:ring-indigo-600">
                          <label for="remember-me" class="ml-2 block text-sm text-gray-900">Remember me</label>
                        </div>

                        <div class="text-sm">
                          <a href="#" class="font-medium text-indigo-600 hover:text-indigo-500">Forgot your password?</a>
                        </div>
                      </div>

                      <div>
                        <button type="submit"
                          class="flex w-full justify-center rounded-md bg-indigo-600 px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600">Sign
                          in</button>
                      </div>
                    </form>
                  </div>
                </div>
              </div>
            </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.left-bg {
  background: url(@/assets/bg-main-desktop.png);
  background-size: cover;
}

.card-front {
  position: relative;
  top: 150px;
  left: 30%;
  width: 100%;
}

.card-back {
  position: relative;
  top: 180px;
  left: 50%;
}
</style>
