<template>
  <div class="gt">
    <button @click="$emit('onclick')">{{ text }}</button>
    <button @click="$emit('onclick')">{{ test }}</button>
  </div>
</template>

<script>
export default {
  props: {
    test: String,
    text: String,
  },
  data() {
    return {
      value: "测试",
    };
  },
};
</script>

<style>
.gt {
  padding: 50px;
}
</style>