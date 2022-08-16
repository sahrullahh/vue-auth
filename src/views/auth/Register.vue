<template>
  <div class="auth-register">
    <form @submit.prevent="handleSubmit">
      <div
        class="card mt-8 px-10 py-5 space-y-7 bg-white rounded-md max-w-xl mx-auto"
      >
        <div class="title-card text-center">
          <h2 class="text-4xl font-bold">Account Register</h2>
        </div>
        <div class="card-body text-left space-y-5">
          <div class="input-box space-y-3">
            <label for="username" class="font-bold">Username</label>
            <input
              v-model="username"
              type="username"
              placeholder=""
              id="username"
              name="username"
              autocomplete="off"
              class="bg-white font-quicksand w-full shadow-sm text-sm border-box px-5 py-3 border-gray-300 outline-none border rounded-lg"
            />
          </div>
          <div class="input-box space-y-3">
            <label for="Email" class="font-bold">Email</label>
            <input
              v-model="email"
              type="email"
              placeholder=""
              id="email"
              name="email"
              autocomplete="off"
              class="bg-white font-quicksand w-full shadow-sm text-sm border-box px-5 py-3 border-gray-300 outline-none border rounded-lg"
            />
          </div>
          <div class="input-box space-y-3">
            <label for="password" class="font-bold">Password</label>
            <input
              v-model="password"
              type="password"
              placeholder=""
              id="password"
              name="password"
              autocomplete="off"
              class="bg-white font-quicksand w-full shadow-sm text-sm border-box px-5 py-3 border-gray-300 outline-none border rounded-lg"
            />
          </div>
          <div class="input-box space-y-3">
            <label for="password" class="font-bold">Confirm Password</label>
            <input
              v-model="confirmPassword"
              type="password"
              placeholder=""
              id="password"
              name="password"
              autocomplete="off"
              class="bg-white font-quicksand w-full shadow-sm text-sm border-box px-5 py-3 border-gray-300 outline-none border rounded-lg"
            />
          </div>
          <button class="bg-green-500 px-8 py-3 rounded text-white">
            Create a account
          </button>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
  import axios from "axios";

  export default {
    name: "Register",
    data() {
      return {
        username: "",
        email: "",
        password: "",
        confirmPassword: "",
      };
    },
    methods: {
      async handleSubmit() {
        const response = await axios.post("register", {
          username: this.username,
          email: this.email,
          password: this.password,
          confirmPassword: this.confirmPassword,
        });
        console.log(response);
      },
    },
    mounted() {},
  };
</script>
