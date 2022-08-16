<template>
  <div id="app" class="font-quicksand">
    <Header />
    <div class="container mx-auto max-w-7xl">
      <router-view />
    </div>
  </div>
</template>
<style>
  body {
    @apply bg-green-400;
  }
</style>
<script>
  import Header from "@/components/Header";

  export default {
    components: {
      Header,
    },
  };
</script>
