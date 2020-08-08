<template>
  <div>
    <h1>Register</h1>
    <UserAuthForm buttonText="Register" :submitForm="registerUser", hasName="true" />
  </div>
</template>

<script>
  import UserAuthForm from '../components/UserAuthForm';
  export default {
    components: {
      UserAuthForm
    },
    methods: {
      async registerUser(registrationinfo){
        await this.$axios.post('/users', registrationinfo)
        this.$auth.loginWith('local', {
          data: registrationinfo
        })
      }
    }
  }
</script>
