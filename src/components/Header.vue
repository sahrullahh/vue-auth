<template>
  <div id="header">
    <header class="header bg-white w-full top-0 border-b">
      <div class="container max-w-7xl mx-auto box-border">
        <div class="flex justify-between flex-wrap gap-4 p-1">
          <div class="flex-shrink-0 flex-wrap p-2">
            <h2 class="text-2xl text-gray-800 font-semibold">VueAuth</h2>
          </div>
          <div class="flex-grow mt-3 ml-4 space-x-4">
            <router-link to="/" class="hover:text-green-400">Home</router-link>
            <router-link to="/" class="hover:text-green-400"
              >Product</router-link
            >
          </div>
          <div class="mt-1 space-x-3">
            <router-link to="/login">
              <button
                class="bg-green-400 hover:bg-green-600 font-semibold text-white px-5 py-2 rounded-md border-none"
              >
                Log in
              </button>
            </router-link>
            <router-link to="/register">
              <button
                class="font-semibold hover:bg-green-50 text-green-400 bg-white px-5 py-2 rounded-md border-none"
              >
                Register
              </button>
            </router-link>
          </div>
        </div>
      </div>
    </header>
  </div>
</template>
