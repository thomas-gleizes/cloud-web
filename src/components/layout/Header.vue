<script>
import Tab from "@/components/layout/Navigation/Tab";

export default {
  name: "Header",
  components: { Tab },
  data() {
    return {
      tabs: [
        { title: "Tab 1", active: true },
        { title: "Tab 2", active: false },
        { title: "Tab 3", active: false }
      ]
    };
  },
  methods: {
    deleteTab(tab) {
      if (this.tabs.length > 1) {
        const index = this.tabs.findIndex(search => search === tab);

        this.tabs.splice(index, 1);
      }

    },
    addTab() {
      this.tabs.push({ title: "new tab", active: false });
    },
    selectTab(tab) {
      this.tabs.forEach(tab => tab.active = false)
      tab.active = true;
    },
  }
};
</script>

<template>
  <header class="flex justify-start py-2 px-20 bg-gray-50 shadow-md border w-screen">
    <div class="mx-5">
      <img class="" width="60" alt="Vue logo" src="../../assets/logo.png" />
    </div>

    <h2 class="text-2xl mx-5 font-bold text-green-600 italic my-auto">Cloud web</h2>
  </header>
  <div class="flex w-100 bg-gray-100 shadow divide-solid divide-x px-2">
    <Tab v-for="tab in tabs" :key="tab.title" v-bind:name="tab.title" v-bind:active="tab.active"
         v-bind:delete-tab="() => deleteTab(tab)" @click="() => selectTab(tab)" />
    <div class="my-auto">
      <i class="p-2 cursor-pointer" @click="addTab">
        <fa icon="plus" size="lg" />
      </i>
    </div>
  </div>
</template>
