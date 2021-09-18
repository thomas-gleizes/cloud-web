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
    }
  },
  data() {
    return {
      hover: false,
      editable: false
    };
  },
  methods: {
    setHover(bool) {
      this.hover = bool;
    },
    setEditable(bool) {
      this.editable = bool;
      if (bool) {
        console.log(bool);
      }
    }
  }
};
</script>

<template>
  <div
    class="px-4 py-1"
    v-bind:class="{ 'bg-white': active }"
    @mouseenter="setHover(true)"
    @mouseleave="setHover(false)"
  >
    <div class="flex">
      <div
        v-on:dblclick="setEditable(true)"
        class="transition duration-75 transform scale-100 hover:scale-105 cursor-pointer"
      >
        <span v-if="!editable" class="text-lg">{{ name }}</span>
        <input v-if="editable" ref="input" class="text-lg w-20 outline-none" />
      </div>
      <div v-bind:class="{ 'invisible': !hover }" class="my-auto opacity-80 pl-2">
        <i @click="deleteTab" class="cursor-pointer">
          <fa icon="times-circle" />
        </i>
      </div>
    </div>
  </div>
</template>
