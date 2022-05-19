<template>
  <button @click="hadclick">我就是一个按钮{{ test }}</button>
</template>

<script>
export default {
  props: ["test"],
  model: {
    prop: "test",
    event: "change",
  },
  methods: {
    hadclick() {
      this.$emit("change", "dsadasdsdas");
    },
  },
};
</script>

<style>
</style>