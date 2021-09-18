<template>
  <Header></Header>
  <main class="w-screen">
    <div class="flex">
      <Folder name="app" />
      <Folder name="code" />
      <File name="test.js" />
    </div>

    <div class="max-w-400 mx-10">
      <Card title="Timeline" />
      <Card title="Metadata" />
    </div>
  </main>
</template>

<script>
import Folder from "./components/common/Folder.vue";
import File from "./components/common/File.vue";

import Header from "@/components/layout/Header";
import Card from "./components/layout/Card";

export default {
  name: "App",
  components: {
    Card,
    Folder, File, Header
  }
};
</script>

<style>

</style>
