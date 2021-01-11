<template>
  <main class="mt-10 mx-auto max-w-7xl px-4 sm:mt-12 sm:px-6 md:mt-16 lg:mt-20 lg:px-8 xl:mt-28">
    <div class="sm:text-center lg:text-left">
      <h1 class="text-4xl tracking-tight font-extrabold text-gray-900 sm:text-5xl md:text-6xl">
        <span class="block xl:inline">Welcome to the best corny jokes of </span>
        <span class="block text-indigo-600 xl:inline">Dad Jokes</span> in the wold
      </h1>
      <p class="mt-3 text-base text-gray-500 sm:mt-5 sm:text-lg sm:max-w-xl sm:mx-auto md:mt-5 md:text-xl lg:mx-0">
        Some teribbly amusing puns that will make you laugh out loud!
      </p>
      <div class="mt-5 sm:mt-8 sm:flex sm:justify-center lg:justify-start">
        <div class="rounded-md shadow">
          <nuxt-link to="/jokes"
            class="w-full flex items-center justify-center px-8 py-3 border border-transparent text-base font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-700 md:py-4 md:text-lg md:px-10">
            View Jokes
          </nuxt-link>
        </div>
        <div class="mt-3 sm:mt-0 sm:ml-3">
          <nuxt-link to="/about"
            class="w-full flex items-center justify-center px-8 py-3 border border-transparent text-base font-medium rounded-md text-indigo-700 bg-indigo-100 hover:bg-indigo-200 md:py-4 md:text-lg md:px-10">
            About Dad Jokes
          </nuxt-link>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
export default {
  head() {
    return {
      title: "Welcome to dad jokes",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Best place for corny dad jokes",
        }
      ]
    }
  }
}
</script>
