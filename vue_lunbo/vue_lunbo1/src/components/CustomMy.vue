<template>
  <div>
    <my-button text="登录" @onclick="login" />
    <my-button text="注册" @onclick="zhuce" />
    <my-button @onclick="changeShow" @click.native="fun" />
    <div v-show="show" class="div1"></div>
  </div>
</template>

<script>
import MyButton from "./MyButton.vue";
export default {
  components: { MyButton },
  data() {
    return {
      show: true,
    };
  },
  methods: {
    changeShow() {
      this.show = !this.show;
    },
    login() {
      console.log("登录");
    },
    zhuce() {
      console.log("注册");
    },
    fun() {
      console.log(1111);
    },
  },
};
</script>

<style>
.div1 {
  width: 300px;
  height: 300px;
  background-color: #ccc;
}
</style>