<script>
export default {
  name: "File",
  props: {
    name: {
      type: String,
      required: true,
      default: null,
    },
  },
};
</script>

<template>
  <div class="border-2 m-2 py-2 w-36 rounded text-center cursor-pointer">
    <div class="text-gray-600">
      <fa icon="file" size="5x" />
    </div>
    <div>{{ name }}</div>
  </div>
</template>
