<script>
import Folder from "./components/common/Folder.vue";
import File from "./components/common/File.vue";
import TimeTo from "@/components/common/TimeTo";
import Header from "@/components/layout/Header";

export default {
  name: "App",
  components: { TimeTo, Header, Folder, File },
  data() {
    return {
      limitDate: new Date()
    }
  }
};
</script>

<template>
  <Header />
  <main class="w-screen">
    <div class="flex m-5">
      <Folder name="app" />
      <Folder name="code" />
      <File name="test.js" />
    </div>
    <div class="text-center mt-10 text-xl">
      <time-to v-bind:limit-date="limitDate" />
    </div>
  </main>
</template>
