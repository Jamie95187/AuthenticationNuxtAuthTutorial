<template>
  <div>
    <form v-model="valid">
      <input v-model="userInfo.name"
                placeholder="Name..."
                label="Name"
                :rules="[required('name')]"
                v-if="hasName" />
      <input v-model="userInfo.email"
                placeholder="Email Address..."
                label="Email"
                :rules="[required('email'), emailFormat()]"/>
      <input v-model="userInfo.password"
                    label="Password"
                    placeholder="Password..."
                    :type="showPassword ? 'text' : 'password'"
                    :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
                    @click:append="showPassword = !showPassword"
                    counter=true
                    :rules="[required('password'), minLength('password', 8)]"/>

      <button @click="submitForm(userInfo)">login</button>
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
          email: 'text1@example.com',
          password: 'test1',
        },
        ...validations
      }
    },
    props: ["submitForm", "buttonText", "hasName"]
  }
</script>
