<template>
  <div>
    <button>{{ num }}</button>
    <sync-demochild :num.sync="num" />
  </div>
</template>

<script>
import SyncDemochild from "./SyncDemochild.vue";
export default {
  components: { SyncDemochild },
  data() {
    return {
      num: 100,
    };
  },
};
</script>

<style>
</style>