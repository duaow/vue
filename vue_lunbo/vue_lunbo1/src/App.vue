<template>
  <div id="app">
    <LunBo />
    <XuanXiang />
    <list-demo />
    <custom-my />
    <sync-deom />
  </div>
</template>

<script>
import CustomMy from "./components/CustomMy.vue";
import ListDemo from "./components/list-demo.vue";
import LunBo from "./components/LunBo.vue";
import SyncDeom from "./components/SyncDeom.vue";
import XuanXiang from "./components/XuanXiang.vue";
export default {
  name: "App",
  components: { LunBo, XuanXiang, ListDemo, CustomMy, SyncDeom },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
