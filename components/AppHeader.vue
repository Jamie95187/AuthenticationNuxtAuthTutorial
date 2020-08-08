<template>
  <div v-if="$auth.loggedIn">
    {{ $auth.user.email }}
    <button text @click="$auth.logout">Logout</button>
    <!-- username -->
    <!-- logout button -->
  </div>
  <div v-else>
    <nuxt-link text to="/login">Login</nuxt-link>
    <nuxt-link text to="/register">Register</nuxt-link>
    <!-- login -->
    <!-- logout -->
  </div>
</template>

<script>
  export default {
    name: 'AppHeader'
  }
</script>
