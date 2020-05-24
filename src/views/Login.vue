<template>
  <div class="p-3 flex justify-center">
    <div class="w-1/2 py-10 flex flex-wrap justify-center border rounded">
      <h1 class="text-3xl w-full text-center">Login Page</h1>
      <span v-if="errors.error" class="text-xs text-red-600">{{
        errors.error
      }}</span>
      <form class="flex flex-wrap justify-center p-2" @submit.prevent="submit">
        <div class="py-2 w-full">
          <input
            type="email"
            v-model="form.email"
            placeholder="Your Awesome Email"
            class="p-2 w-full rounded border shadow"
          />
        </div>
        <div class="py-2 w-full">
          <input
            type="password"
            v-model="form.password"
            placeholder="********"
            class="p-2 w-full rounded border shadow"
          />
        </div>

        <div class="py-2 w-full">
          <input
            type="submit"
            value="Login"
            class="px-3 py-2 bg-pink-700 rounded shadow border text-white w-full"
          />
        </div>
      </form>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Login",
  data() {
    return {
      form: {
        email: "",
        password: "",
      },
      errors: {},
    };
  },
  methods: {
    submit() {
      axios.post("http://localhost:4000/login", this.form).catch((e) => {
        this.errors = e.response.data;
      });
    },
  },
};
</script>
