<template>
    <div class="py-12 px-5 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <search-jokes v-on:search-text="searchText"></search-jokes>

        <div class="mt-10">
          <dl class="space-y-10 md:space-y-0 md:grid md:grid-cols-2 md:gap-x-8 md:gap-y-10">
            <joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke"></joke>
          </dl>
        </div>
      </div>
    </div>
</template>

<script>
import axios from 'axios';
import Joke from '../../components/Joke.vue'
import SearchJokes from '../../components/SearchJokes.vue'

export default {
  components: {
    Joke,
    SearchJokes
  },
  data() {
    return {
      jokes: []
    }
  },
  async created() {
    const config = {
      headers: {
        Accept: 'application/json'
      }
    }

    try {
      const res = await axios.get('https://icanhazdadjoke.com/search', config);

      this.jokes = res.data.results;
    } catch (error) {
      console.log(error)
    }
  },
  methods: {
    async searchText(text) {
      const config = {
        headers: {
          Accept: 'application/json'
        }
      }

      try {
        const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`, config);

        this.jokes = res.data.results;
      } catch (error) {
        console.log(error)
      }
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
