<template>
  <header class="bg-white shadow h-16 flex justify-between items-stretch">
    <router-link
      :to="{ name: 'home' }"
      class="inline-flex items-center h-full px-5 text-blue-800 font-bold"
    >
      Home
    </router-link>
    <div class="flex items-center gap-1">
      <router-link
        :to="{ name: 'byName' }"
        class="inline-flex items-center px-2 h-full transition-colors hover:bg-blue-900 hover:text-white"
      >
        search meals
      </router-link>
      <router-link
        :to="{ name: 'byLetter' }"
        class="inline-flex items-center px-2 h-full transition-colors hover:bg-yellow-700 hover:text-white"
      >
        by letter
      </router-link>
      <router-link
        :to="{ name: 'ingredients' }"
        class="inline-flex items-center px-2 h-full transition-colors hover:bg-blue-600 hover:text-white"
      >
        by ingredients
      </router-link>

      <router-link
        :to="{ name: 'guest' }"
        class="inline-flex items-center px-2 h-full transition-colors hover:bg-blue-600 hover:text-white"
      >
        Login
      </router-link>

      <router-link
        :to="{ name: 'registiration' }"
        class="inline-flex items-center px-2 h-full transition-colors hover:bg-blue-600 hover:text-white"
      >
        Regi
      </router-link>
      <router-link
        :to="{ name: 'forgottenPassword' }"
        class="inline-flex items-center px-2 h-full transition-colors hover:bg-blue-600 hover:text-white"
      >
      ForgottenPassword
      </router-link>
    </div>
  </header>
</template>
