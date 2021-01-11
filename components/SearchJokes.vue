<template>
  <form @submit.prevent="onSubmit" class="flex w-full max-w-sm mx-auto space-x-3">
    <input class="flex-1 appearance-none border border-transparent w-full py-2 px-4 bg-white text-gray-700 placeholder-gray-400 shadow-md rounded-lg text-base focus:outline-none focus:ring-2 focus:ring-indigo-600 focus:border-transparent" type="text" v-model="text" placeholder="Search Jokes...">
    <button class="flex-shrink-0 bg-indigo-600 text-white text-base font-semibold py-2 px-4 rounded-lg shadow-md hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 focus:ring-offset-indigo-200">
      Search Jokes
    </button>
  </form>
</template>

<script>
export default {
  name: 'SearchJokes',
  data() {
    return {
      text: ''
    }
  },
  methods: {
    onSubmit() {
      this.$emit('search-text', this.text);
      this.text = '';
    }
  },
}
</script>

<style lang="">

</style>
