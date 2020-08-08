<template>
  <div>
    <h1>Login</h1>
    <UserAuthForm buttonText="Login" :submitForm="loginUser" />
  </div>
</template>

<script>
  import UserAuthForm from '../components/UserAuthForm';
  export default {
    components: {
      UserAuthForm
    },
    methods: {
      loginUser(loginfo){
        this.$auth.loginWith('local', {
          data: logininfo
        })
        alert("You pressed a button")
      }
    }
  }
</script>
