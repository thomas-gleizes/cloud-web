<template>
  <Header></Header>
  <main class="w-screen">
    <div class="flex">
      <Folder name="app" />
      <Folder name="code" />
      <File name="test.js" />
    </div>
  </main>
</template>

<script>
import Folder from "./components/common/Folder.vue";
import File from "./components/common/File.vue"

import Header from "@/components/layout/Header";

export default {
  name: "App",
  components: {
    Folder, File, Header,
  },
};
</script>

<style>

</style>
