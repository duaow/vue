<template>
  <div class="box" @mouseenter="changeInt(true)" @mouseleave="changeInt(false)">
    <div class="img">
      <img
        v-for="item in imgArr"
        :key="item.id"
        :src="item.url"
        alt="暂无图片"
        :class="item.id === num ? 'active' : ''"
      />
    </div>

    <ul>
      <li
        @mouseenter="clickImg(item.id)"
        v-for="item in imgArr"
        :key="item.id"
        :class="item.id === num ? 'active' : ''"
      ></li>
    </ul>

    <i @click="clickIcon('prev')" class="iconfont icon-zuojiantou i1"></i>
    <i @click="clickIcon('next')" class="iconfont icon-youjiantou i2"></i>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num: 0,
      time: null,
      imgArr: [
        {
          id: 0,
          url: "https://img14.360buyimg.com/babel/s1180x940_jfs/t1/97055/7/26936/83947/62736920E1209b3f3/3a6cddc53b4e96b0.jpg.webp",
        },
        {
          id: 1,
          url: "https://img12.360buyimg.com/pop/s1180x940_jfs/t1/214519/29/15688/100874/623999a2E8e0cb1a7/a059d1b30b98eb18.jpg.webp",
        },
        {
          id: 2,
          url: "https://imgcps.jd.com/ling4/8452203/5Lqs6YCJ5aW96LSn/5L2g5YC85b6X5oul5pyJ/p-5bd8253082acdd181d02fa68/6c05dae6/cr/s/q.jpg",
        },
        {
          id: 3,
          url: "https://imgcps.jd.com/ling4/100026667880/5Lqs6YCJ5aW96LSn/5L2g5YC85b6X5oul5pyJ/p-5bd8253082acdd181d02fa7f/5249df17/cr/s/q.jpg",
        },
      ],
    };
  },

  methods: {
    start() {
      clearInterval(this.time);
      this.time = setInterval(() => {
        this.num++;
        if (this.num === this.imgArr.length) {
          this.num = 0;
        }
      }, 2000);
    },
    clickIcon(val) {
      if (val === "next") {
        this.num++;
        if (this.num === this.imgArr.length) {
          this.num = 0;
        }
      } else {
        this.num--;
        if (this.num < 0) {
          this.num = this.imgArr.length - 1;
        }
      }
    },
    clickImg(index) {
      this.num = index;
    },
    changeInt(val) {
      if (val) {
        clearInterval(this.time);
      } else {
        this.start();
      }
    },
  },
  mounted() {
    this.start();
  },
};
</script>

<style>
.box {
  width: 590px;
  height: 470px;
  overflow: hidden;
  position: relative;
  margin: 0 auto;
  margin-top: 50px;
}
.img {
  width: 100%;
  height: 100%;
}
img {
  position: absolute;
  left: 0;
  top: 0;
  transition: all 1s;
  z-index: 1;
  width: 100%;
  height: 100%;
  opacity: 0;
}

img.active {
  z-index: 2;
  opacity: 1;
}
ul,
li {
  list-style: none;
}
.box ul {
  position: absolute;
  z-index: 5;
  left: 50%;
  bottom: 40px;
  margin-left: -44px;
}
.box ul li {
  float: left;
  margin-right: 4px;
  width: 10px;
  height: 10px;
  border-radius: 50%;
  border: 4px solid transparent;
  display: block;
  background-color: rgba(255, 255, 255, 0.7);
  background-clip: content-box;
}
.box li.active {
  border: 4px solid rgba(255, 255, 255, 0.7);
  background-color: #fff;
}
i {
  position: absolute;
  z-index: 5;

  top: 50%;
  margin-top: -15px;
  font-size: 30px !important;
  cursor: pointer;
}
.i1 {
  left: 0;
}
.i2 {
  right: 0;
}
@import "//at.alicdn.com/t/font_3383558_y3j1g3qpgmf.css";
@import "../assets/ty.css";
</style>