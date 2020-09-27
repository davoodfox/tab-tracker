<template>
  <div>
    <h1>Register</h1>

    <input v-model="email" type="email" name="email" placeholder="email" />
    <input
      v-model="password"
      type="password"
      name="password"
      placeholder="password"
    />
    <button @click="register">Register</button>
  </div>
</template>

<script>
import Auth from "@/services/Auth";
export default {
  data() {
    return {
      email: "",
      password: ""
    };
  },
  methods: {
    async register() {
      const response = await Auth.register({
        email: this.email,
        password: this.password
      });
      console.log(response.data);
    }
  }
};
</script>

<style lang="scss" scoped>
</style>