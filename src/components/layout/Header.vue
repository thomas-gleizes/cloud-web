<script>
import TabsBar from "@/components/layout/navigation/TabsBar";
import Clock from "../common/Clock";

export default {
  name: "Header",
  components: { TabsBar, Clock }
};
</script>

<template>
  <header>
    <div class="flex justify-between py-2 px-3 bg-gray-50 shadow-md border w-screen">
      <div class="flex justify-start select-none">
        <div class="mx-5 transform transition hover:scale-110">
          <img width="60" alt="Vue logo" src="../../assets/logo.png" />
        </div>

        <h2 class="text-2xl mx-5 font-bold text-green-600 italic my-auto">Cloud web</h2>
      </div>
      <div class="flex justify-end my-auto px-4 text-lg">
        <span class="flex font-bold select-none">
          <i class="mr-2">
            <fa icon="clock" />
          </i>
          <clock />
        </span>
      </div>
    </div>
  </header>
  <tabs-bar />
</template>
