<template>
  <v-container>
    <v-form v-model="valid">
      <v-text-field v-model="loginInfo.email"
                    label="Email"
                    :rules="[required('email'), emailFormat()]" />
      <v-text-field v-mdodel="loginInfo.password"
                    label="Password"
                    :type="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
                    @click:append="showPassword = !showPassword"
                    counter=true
                    :rules="[required('password'), minLength('password', 8)]"/>
      <v-btn @click="loginUser" :disabled="!valid">Login</v-btn>
    </v-form>
  </v-container>
</template>

<script>
  import validations from '../utils/validation';

  export default {
    data() {
      return {
        showPassword: true,
        logInfo: {
          email: '',
          password: ''
        },
        ...validations
      }
    }
  }
</script>
