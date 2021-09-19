<script>
import Tab from "@/components/layout/navigation/Tab";

export default {
  name: "TabsBar",
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
      this.tabs.forEach(tab => tab.active = false);
      tab.active = true;
    },
    editName(tab, value) {
      const index = this.tabs.findIndex(search => search === tab);
      this.tabs[index] = value;
    }
  }
};
</script>

<template>
  <div class="flex w-100 bg-gray-100 shadow divide-solid divide-x px-2">
    <Tab
      v-for="tab in tabs" :key="tab.title"
      v-bind:name="tab.title"
      v-bind:active="tab.active"
      v-bind:delete-tab="() => deleteTab(tab)"
      @click="() => selectTab(tab)"
    />
    <div class="my-auto">
      <i class="p-2 cursor-pointer" @click="addTab">
        <fa icon="plus" size="lg" />
      </i>
    </div>
  </div>
</template>