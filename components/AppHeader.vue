<template>
  <div v-if="$auth.loggedIn">
    {{ $auth.user.email }}
    <button text>Logout</button>
    <!-- username -->
    <!-- logout button -->
  </div>
  <div v-else>
    <button text to="/login">Login</button>
    <button text to="/register">Register</button>
    <!-- login -->
    <!-- logout -->
  </div>
</template>

<script>
  export default {
    name: 'AppHeader'
  }
</script>
