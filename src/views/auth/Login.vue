<template>
  <div class="auth-login">
    <form @submit.prevent="handleLogin">
      <div
        class="card mt-8 px-10 py-5 space-y-5 bg-white rounded-md max-w-xl mx-auto"
      >
        <div class="title-card text-center">
          <h2 class="text-4xl font-bold">Log in</h2>
        </div>
        <div class="card-body text-left space-y-5">
          <div class="input-box space-y-3">
            <label for="email" class="font-bold">email</label>
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
          <button class="bg-green-500 px-8 py-3 rounded text-white">
            Login
          </button>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
  import axios from "axios";
  export default {
    data() {
      return {
        email: "",
        password: "",
      };
    },
    methods: {
      async handleLogin() {
        var data = JSON.stringify({
          email: this.email,
          password: this.password,
        });

        var config = {
          method: "post",
          url: "http://192.168.0.103:8080/api/v1/users/login",
          headers: {
            "Access-Control-Allow-Origin": "*",
            "Content-Type": "application/json",
          },
          data: data,
        };

        axios(config)
          .then(function (response) {
            console.log(JSON.stringify(response.data));
          })
          .catch(function (error) {
            console.log(error);
          });
      },
    },
  };
</script>
