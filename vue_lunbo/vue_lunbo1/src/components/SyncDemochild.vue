<template>
  <button @click="hadclick">按钮</button>
</template>

<script>
export default {
  props: {},
  methods: {
    hadclick() {
      this.$emit("update:num", 10000);
    },
  },
};
</script>

<style>
</style>