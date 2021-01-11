<template>
  <nuxt-link :to="'jokes/' + id">
    <div class="flex">
      <div class="flex-shrink-0">
        <div class="flex items-center justify-center h-12 w-12 rounded-md bg-indigo-500 text-white">
          <!-- Heroicon name: annotation -->
          <svg class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 8h10M7 12h4m1 8l-4-4H5a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v8a2 2 0 01-2 2h-3l-4 4z" />
          </svg>
        </div>
      </div>
      <div class="ml-4">
        <dd class="text-base text-gray-500">
          {{ joke }}
        </dd>
      </div>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  name: 'Joke',
  props: ['joke', 'id']
}
</script>

<style>
  .joke {
    padding: 1rem;
    border: 1px dotted #ccc;
    margin: 1rem 0;
  }
</style>
