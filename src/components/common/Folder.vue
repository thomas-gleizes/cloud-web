<template>
  <div class="border-2 m-2 py-2 w-36 rounded text-center cursor-pointer" @mouseenter="toggleHover('folder-open')" @mouseleave="toggleHover('folder')">
    <div class="text-blue-500">
      <fa v-bind:icon="icon" size="5x" />
    </div>
    <div>{{ name }}</div>
  </div>
</template>

<script>
export default {
  name: "Folder",
  props: {
    name: {
      type: String,
      required: true,
      default: null
    }
  },
  data() {
    return {
      icon: "folder"
    };
  },
  methods: {
    toggleHover(icon) {
      this.icon = icon;
    }
  }
};
</script>
