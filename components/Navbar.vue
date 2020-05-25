<template>
  <header
    class="bg-gray-900 sm:flex sm:justify-between sm:items-center sm:px-24 sm:py-4"
  >
    <div class="flex items-center justify-between px-4 py-3 sm:p-0">
      <nuxt-link
        to="/"
        class="text-xl font-semibold tracking-tight border-b-2 border-gray-900"
      >
        <span class="text-white">Sky</span
        ><span class="text-teal-300">break</span>
      </nuxt-link>
      <div class="sm:hidden">
        <button
          class="block text-gray-500 hover:text-white focus:text-white focus:outline-none"
          type="button"
          @click="isOpen = !isOpen"
        >
          <svg class="h-6 w-6 fill-current" viewBox="0 0 24 24">
            <path
              v-if="isOpen"
              fill-rule="evenodd"
              d="M18.278 16.864a1 1 0 0 1-1.414 1.414l-4.829-4.828-4.828 4.828a1 1 0 0 1-1.414-1.414l4.828-4.829-4.828-4.828a1 1 0 0 1 1.414-1.414l4.829 4.828 4.828-4.828a1 1 0 1 1 1.414 1.414l-4.828 4.829 4.828 4.828z"
            />
            <path
              v-if="!isOpen"
              fill-rule="evenodd"
              d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"
            />
          </svg>
        </button>
      </div>
    </div>
    <nav
      :class="isOpen ? 'block' : 'hidden'"
      class="px-2 pt-2 pb-4 sm:flex sm:p-0 text-center text-gray-300 font-semibold lowercase sm:space-x-2"
    >
      <nuxt-link
        to="/events"
        class="block px-2 py-1 rounded hover:bg-teal-900 border-b-2 border-gray-900"
        active-class="sm:text-teal-300 border-b-2 sm:border-teal-300"
        >Events</nuxt-link
      >
      <nuxt-link
        to="/players"
        class="block px-2 py-1 rounded hover:bg-teal-900 border-b-2 border-gray-900"
        active-class="sm:text-teal-300 border-b-2 sm:border-teal-300"
        >Players</nuxt-link
      >
      <nuxt-link
        to="/teams"
        class="block px-2 py-1 rounded hover:bg-teal-900 border-b-2 border-gray-900"
        active-class="sm:text-teal-300 border-b-2 sm:border-teal-300"
        >Teams</nuxt-link
      >
      <nuxt-link
        to="/rating"
        class="block px-2 py-1 rounded hover:bg-teal-900 border-b-2 border-gray-900"
        active-class="sm:text-teal-300 border-b-2 sm:border-teal-300"
        >Rating</nuxt-link
      >
    </nav>
    <a
      v-if="$auth.loggedIn"
      class="px-4 py-1 bg-teal-900 rounded font-semibold text-sm"
      href="#"
      @click="$auth.logout()"
      >Logout</a
    >
    <a
      v-else
      class="px-4 py-1 bg-teal-900 rounded font-semibold text-sm"
      href="#"
      @click="$auth.loginWith('auth0')"
      >Login</a
    >
  </header>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false
    }
  },
  methods: {
    login: () => {
      this.$auth.loginWith('auth0')
    }
  }
}
</script>
