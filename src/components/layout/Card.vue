<template>
  <div class="border mb-2 rounded-lg shadow-md">
    <div class="px-2 py-1 flex justify-between">
      <h2 class="text-lg">{{ title }}</h2>
      <button @click="toggle" class="transition transform hover:text-blue-700 hover:scale-105 duration-150 p-1.5">
        <fa v-if="!open" icon="minus" />
        <fa v-if="open" icon="plus" />
      </button>
    </div>
    <div class="border-t bg-white p-1">
      {{ open }}
    </div>
  </div>
</template>

<script>

export default {
  name: "Card",
  props: {
    title: {
      type: String,
      required: true
    },
    defaultOpen: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      open: false
    };
  },
  methods: {
    toggle() {
      this.open = !this.open;
    }
  }
};

</script>
