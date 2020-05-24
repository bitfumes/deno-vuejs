<template>
  <div id="app">
    <div class="p-2 text-white bg-pink-800">
      <router-link v-if="loggedIn" class="mr-4" to="/">Home</router-link>
      <router-link v-else class="mr-4" to="/login">Login</router-link>
      <router-link class="mr-4" to="/about">About</router-link>
      <a v-if="loggedIn" href="" @click="logout">Logout</a>
    </div>
    <router-view />
  </div>
</template>

<script>
export default {
  data(){
    return {
      loggedIn : window.loggedIn
    }
  },
  methods:{
    logout(){
      window.loggedIn = false
      window.location = '/'
      this.$cookies.remove('token')
    }
  }
}
</script>
<style></style>
