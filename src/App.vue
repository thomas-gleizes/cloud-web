<template>
  <div class="w-screen">
    <img class="mx-auto" alt="Vue logo" src="./assets/logo.png" />
    <h1 class="text-3xl font-bold text-green-500">Welcome to Your Vue.js App</h1>
    <div class="flex">
      <Folder name="app" />
      <Folder name="app" />
    </div>
  </div>
</template>

<script>
import Folder from "./components/Folder.vue";

export default {
  name: "App",
  components: {
    Folder,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
