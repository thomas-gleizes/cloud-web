<script>
export default {
  name: "Tab",
  props: {
    name: {
      type: String,
      required: true
    },
    active: {
      type: Boolean,
      required: true
    },
    deleteTab: {
      type: Function,
      required: true
    },
  },
  data() {
    return {
      hover: false,
      editable: false,
      value: ""
    };
  },
  methods: {
    handleHover(bool) {
      this.hover = bool;
    },
    handleEditable(bool) {
      this.editable = bool;
      if (bool)
        this.$refs.input.focus();
    },
  }
};
</script>

<template>
  <div
    class="px-4 py-1"
    v-bind:class="{ 'bg-white': active }"
    @mouseenter="handleHover(true)"
    @mouseleave="handleHover(false)"
  >
    <div class="flex">
      <div
        v-on:dblclick="handleEditable(true)"
        class="transition duration-75 transform scale-100 hover:scale-105 cursor-pointer"
      >
        <span v-show="!editable" class="text-lg select-none">{{ value || name }}</span>
        <input v-show="editable" @blur="handleEditable(false)" v-bind:value="name" ref="input"
               class="text-lg w-20 outline-none" />
      </div>
      <div v-bind:class="{ 'invisible': !hover }" class="my-auto opacity-80 pl-2">
        <i @click="deleteTab" class="cursor-pointer">
          <fa icon="times-circle" />
        </i>
      </div>
    </div>
  </div>
</template>
