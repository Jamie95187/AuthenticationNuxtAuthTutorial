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
      registerUser(registrationinfo){
        alert("You pressed a button")
      }
    }
  }
</script>
