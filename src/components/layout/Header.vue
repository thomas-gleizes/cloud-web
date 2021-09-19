<script>
import TabsBar from "@/components/layout/navigation/TabsBar";

export default {
  name: "Header",
  components: { TabsBar }
};
</script>

<template>
  <header>
    <div class="flex justify-start py-2 px-20 bg-gray-50 shadow-md border w-screen">
      <div class="mx-5">
        <img width="60" alt="Vue logo" src="../../assets/logo.png" />
      </div>

      <h2 class="text-2xl mx-5 font-bold text-green-600 italic my-auto">Cloud web</h2>
    </div>
  </header>
  <tabs-bar />
</template>
