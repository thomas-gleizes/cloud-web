<script>
import TabsBar from "@/components/layout/navigation/TabsBar";
import Clock from "../common/Clock";

export default {
  name: "Header",
  components: { TabsBar, Clock },
};
</script>

<template>
  <header>
    <div class="flex justify-between py-2 px-3 bg-gray-50 shadow-md border w-screen">
      <div class="flex justify-start">
        <div class="mx-5">
          <img width="60" alt="Vue logo" src="../../assets/logo.png" />
        </div>

        <h2 class="text-2xl mx-5 font-bold text-green-600 italic my-auto">Cloud web</h2>
      </div>
      <div class="flex justify-end my-auto text-lg">
        <Clock />
      </div>
    </div>
  </header>
  <tabs-bar />
</template>
