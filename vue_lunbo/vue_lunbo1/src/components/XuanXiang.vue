<template>
  <div class="box1">
    <ul>
      <li><a @click.prevent="click" href="">话费</a></li>
      <li><a @click.prevent="click1" href="">机票</a></li>
      <li><a @click.prevent="click2" href="">酒店</a></li>
    </ul>
    <div class="box2">
      <div class="box2-1" v-show="show">
        <h2>充话费</h2>
      </div>
      <div class="box2-2" v-show="show1" :style="{ backgroundColor: bgc }">
        <h2>机票</h2>
      </div>
      <div class="box2-3" v-show="show2" :style="{ backgroundColor: bgc1 }">
        <h2>酒店</h2>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: true,
      show1: false,
      show2: false,
      bgc: "red",
      bgc1: "green",
    };
  },
  methods: {
    click() {
      (this.show = true), (this.show1 = false), (this.show2 = false);
    },
    click1() {
      (this.show = false), (this.show1 = true), (this.show2 = false);
    },
    click2() {
      (this.show = false), (this.show1 = false), (this.show2 = true);
    },
  },
};
</script>

<style>
.box1 {
  width: 200px;
  height: 300px;
  margin: 0 auto;
  background-color: turquoise;
  border: 2px solid #ccc;
  margin-top: 50px;
  margin-bottom: 50px;
}
.box1 ul {
  width: 100%;
  height: 100px;
}
.box1 li {
  float: left;
  text-align: center;
}
.box1 li:first-child a {
  padding: 0 !important;
}
.box1 li a {
  width: 60px;
  height: 100px;
  line-height: 100px;
  text-align: center;
  font-size: 16px;
  font-weight: 500;
  padding-left: 10px;
  display: inline-block;
}
.box2 {
  width: 100%;
  height: 200px;
  position: relative;
}
.box2 div:first-child {
  z-index: 2;
}
.box2 div {
  position: absolute;
  left: 0;
  top: 0;
  z-index: 1;
  width: 100%;
  height: 100%;
  text-align: center;
  line-height: 200px;
}
@import "../assets/ty.css";
</style>