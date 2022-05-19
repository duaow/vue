<template>
  <div class="dada">
    <ul v-if="numbers.length" class="clearfix">
      <li v-for="(item, index) in numbers" :key="item.id">
        {{ item.name + index }}
      </li>
    </ul>
    <button>{{ count }}</button>
    <button @click="fun(100, $event)"></button>
    <button @click="add">+</button>
    <button @click="count = $event.pageX">X</button>
    <!-- <template v-for="item in numbers">
      <p :key="item.id">{{ item.id }}</p>
      <span :key="item.name">{{ item.name }}</span>
    </template> -->
    <list-demo-1
      v-model="test"
      v-for="item in numbers"
      :key="item.id"
      v-bind="item"
    />
    <input @keydown="han1" type="text" v-model="usename" />
    <button @click="han">输出</button>
    <div @click.once="div1" class="div1">
      <div @click.self="div2" class="div2">
        <div @click="div3" class="div3"></div>
      </div>
    </div>
    <label for="vue">vue</label>
    <input v-model="arr" type="checkbox" value="vue" id="vue" />
    <label for="react">react</label>
    <input v-model="arr" type="checkbox" value="react" id="react" />
    <label for="angular">angular</label>
    <input v-model="arr" type="checkbox" value="angular" id="angular" />
    <hr />
    <input v-model="agree" type="checkbox" id="agree" />
    <label for="agree">是否选择</label>
    <hr />
    <label for="nan">男</label>
    <input v-model="sex" type="radio" value="男" id="nan" />
    <label for="nv">女</label>
    <input v-model="sex" type="radio" value="女" id="nv" />
    <select v-model="sel">
      <option value="A">A</option>
      <option value="B">B</option>
      <option value="C">C</option>
      <option value="D">D</option>
    </select>
    <hr />
    <input v-model.number="text" type="text" name="" id="" />
    <input v-model.trim="test" type="text" name="" id="" />
    <my-button v-model="test" />
    <v-mode v-model="test" />
  </div>
</template>

<script>
import listDemo1 from "./list-demo1.vue";
import MyButton from "./MyButton.vue";
import VMode from "./VMode.vue";
export default {
  components: { listDemo1, MyButton, VMode },
  data() {
    return {
      count: 0,
      usename: "23",
      text: "111",
      test: "hello world",
      numbers: [
        {
          id: 1,
          name: "面包",
        },
        {
          id: 2,
          name: "馒头",
        },
        {
          id: 3,
          name: "米饭",
        },
        {
          id: 4,
          name: "面条",
        },
      ],
      arr: ["vue", "react"],
      agree: true,
      sex: "男",
      sel: "C",
    };
  },
  methods: {
    fun(num, e) {
      this.count = num;
      console.log(e);
    },
    add(event) {
      this.count++;
      console.log(event);
    },
    han1() {
      console.log(this.usename);
    },
    han() {
      console.log(this.usename);
      console.log(this.arr);
      console.log(this.sex);
      console.log(this.agree);
      console.log(this.sel);
      console.log(this.text);
      console.log(this.test);
    },
    div1() {
      console.log("我是大盒子");
    },
    div2() {
      console.log("我是中盒子");
    },
    div3() {
      console.log("我是小盒子");
    },
  },
};
</script>

<style>
.dada {
  margin: 0 auto;
  width: 500px;
}
.dada li {
  width: 20px;
  height: 20px;
  background-color: red;
  text-align: center;
  line-height: 20px;
  float: left;
  margin-right: 10px;
}
.div1 {
  width: 400px;
  height: 400px;
  background-color: red;
}
.div2 {
  width: 200px;
  height: 200px;
  background-color: green;
}
.div3 {
  width: 100px;
  height: 100px;
  background-color: yellow;
}
</style>