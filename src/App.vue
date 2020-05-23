<template>
  <div id="app">
    <div class="p-2 text-white bg-pink-800">
      <router-link class="mr-4" to="/">Home</router-link>
      <router-link class="mr-4" to="/login">Login</router-link>
      <router-link class="mr-4" to="/about">About</router-link>
    </div>
    <router-view />
  </div>
</template>

<style></style>
