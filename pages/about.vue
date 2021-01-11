<template>
  <!-- This example requires Tailwind CSS v2.0+ -->
  <div class="py-12 bg-white overflow-hidden sm:rounded-lg">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="px-4 py-5 sm:px-6">
        <h3 class="text-lg leading-6 font-medium text-gray-900">
          About Apps
        </h3>
        <p class="mt-1 max-w-2xl text-sm text-gray-500">
          Detail about application.
        </p>
      </div>
      <div class="border-t border-gray-200">
        <dl>
          <div v-for="(info, index) in infos" :key="info.key" :class="((index % 2 ) ? 'bg-white-50' : 'bg-gray-50') + ' px-4 py-5 sm:grid sm:grid-cols-3 sm:gap-4 sm:px-6'">
            <dt class="text-sm font-medium text-gray-500">
              {{ info.key }}
            </dt>
            <dd class="mt-1 text-sm text-gray-900 sm:mt-0 sm:col-span-2">
              {{ info.value }}
            </dd>
          </div>
        </dl>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      infos: [
        {
          key: 'App Name',
          value: 'Dad Jokes'
        },
        {
          key: 'Description',
          value: 'Some teribbly amusing puns that will make you laugh out loud!'
        },
        {
          key: 'Techs',
          value: 'Vue, Nuxt, Tailwind CSS'
        },
        {
          key: 'Creator',
          value: 'stefanuscc'
        }
      ]
    }
  },
  head() {
    return {
      title: "About the App",
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
