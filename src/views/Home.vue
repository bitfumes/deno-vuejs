<template>
  <div class="text-center">
    <h1 class="text-3xl">Welcome, {{user.name}}</h1>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      user: {}
    };
  },
  created() {
    const token = this.$cookies.get("token");
    axios.defaults.headers.Authorization = `Bearer ${token}`;
    axios.get("http://localhost:4000/me").then(res => {
      this.user = res.data;
    });
  }
};
</script>

<style></style>
