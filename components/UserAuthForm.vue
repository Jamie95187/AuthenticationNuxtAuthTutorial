<template>
  <div>
    <form v-model="valid">
      <textarea v-model="userInfo.name"
                placeholder="Name..."
                label="Name"
                :rules="[required('name')]"
                v-if="hasName" />
      <textarea v-model="userInfo.email"
                placeholder="Email Address..."
                label="Email"
                :rules="[required('email'), emailFormat()]"/>
      <textarea v-model="userInfo.password"
                    label="Password"
                    placeholder="Password..."
                    :type="showPassword ? 'text' : 'password'"
                    :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
                    @click:append="showPassword = !showPassword"
                    counter=true
                    :rules="[required('password'), minLength('password', 8)]"/>

      <button @click="submitForm(userInfo)" :disabled="!valid">{{ buttonText }}</button>
    </form>
  </div>
</template>

<script>
  import validations from "../utils/validation"

  export default {
    data() {
      return {
        valid: false,
        showPassword: false,
        userInfo: {
          email: '',
          password: '',
        },
        ...validations
      }
    },
    props: ["submitForm", "buttonText", "hasName"]
  }
</script>
