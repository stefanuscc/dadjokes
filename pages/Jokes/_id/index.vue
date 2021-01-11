<template>
  <div class="px-5 bg-white">
    <div class="max-w-7xl mx-auto py-12 px-4 sm:px-6">
      <h2 class="text-3xl font-extrabold tracking-tight text-gray-900 sm:text-4xl">
        <span class="block">{{ joke }}</span>
        <span class="block text-indigo-600 text-sm mt-2">Joke ID: {{ $route.params.id }}</span>
      </h2>
      <div class="mt-8 lex">
        <div class="inline-flex rounded-md shadow">
          <nuxt-link to="/jokes" class="inline-flex items-center justify-center px-5 py-3 border border-transparent text-base font-medium rounded-md text-indigo-600 bg-white hover:bg-indigo-50">
            Back to Jokes
          </nuxt-link>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      joke: ""
    }
  },
  async created() {
    const config = {
      headers: {
        Accept: 'application/json'
      }
    }

    try {
      const res = await axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id}`, config);

      this.joke = res.data.joke;
    } catch (error) {
      console.log(error)
    }
  },
  head() {
    return {
      title: "Dad Jokes",
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

<style lang="stylus">

</style>
