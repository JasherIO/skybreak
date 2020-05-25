<template>
  <div>
    <navbar />
    <main class="container mx-auto py-8">
      <nuxt />
    </main>
    <!-- <footer /> -->
  </div>
</template>

<script>
import Navbar from '~/components/Navbar.vue'

export default {
  components: {
    Navbar
  }
}
</script>

<style>
body {
  @apply bg-gray-900;
  @apply text-white;
}
</style>
