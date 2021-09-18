<template>
  <div class="border m-2 p-4 rounded">
    <div>
      <fa icon="folder" size="6x" />
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
      default: null,
    },
  },
};
</script>
