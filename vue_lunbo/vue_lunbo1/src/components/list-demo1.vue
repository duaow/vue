<template>
  <div>
    <p>
      {{ id }}
    </p>
    <span> {{ name }}</span>
    <button>我是一个按钮{{ value }}</button>
  </div>
</template>

<script>
export default {
  props: {
    id: {
      type: Number,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    value: String,
  },
};
</script>

<style>
</style>