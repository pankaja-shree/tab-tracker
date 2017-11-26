<template>
  <div class="register">
    <h1>Register</h1>
    <input v-model="email" type="email" placeholer="email"><br>
    <input v-model="password" type ="password"><br>
    <input type = "submit" value = "submit" @click="register">
  </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'
export default {
  data() {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    async register () {
      const response = await AuthenticationService.register({
        email: this.email,
        password: this.password,
      });
      console.log(response.data.message)
    },
  },
};
</script>
