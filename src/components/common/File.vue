<script>
export default {
  name: "File",
  props: {
    name: {
      type: String,
      required: true,
      default: null
    }
  }
};
</script>

<template>
  <div
    class="border-2 m-2 py-2 w-36 rounded text-center cursor-pointer transform transition hover:scale-110 duration-200"
  >
    <div class="text-gray-600">
      <fa icon="file-code" size="5x" />
    </div>
    <div class="select-none">{{ name }}</div>
  </div>
</template>
