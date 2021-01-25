<!--
 * @Author: your name
 * @Date: 2021-01-21 14:55:11
 * @LastEditTime: 2021-01-25 10:35:18
 * @LastEditors: Please set LastEditors
 * @Description: In User Settings Edit
 * @FilePath: \vue-swiper\src\views\Swiper.vue
-->

<template>
  <div class="swiper">
    <!-- <ul> -->
    <div class="swiper-group">
      <transition-group tag="ul" name="img" class="swiper-ul">
        <li v-for="(item, index) in imgList" :key="index" v-if="index === num">
          <!-- <img src="@/assets/img/1.jpg" alt=""> -->
          <img :src="item" alt="this is img" class="img" />
        </li>
      </transition-group>
    </div>
    <!-- </ul> -->
    <div class="bar">
      <span
        v-for="(item, index) in imgList"
        :key="index"
        :class="{ active: index === num }"
        @click="numChange(index)"
      ></span>
    </div>
  </div>
</template>

<script>
export default {
  name: "Swiper",
  data() {
    return {
      num: 0,
      timer: null,
      imgList: [
        require("../assets/img/1.jpg"),
        require("../assets/img/2.jpg"),
        require("../assets/img/3.jpg"),
        require("../assets/img/4.jpg"),
      ],
    };
  },
  created() {
    this.$nextTick(() => {
      this.numTime();
    });
  },
  methods: {
    numIncrease() {
      this.num++;
      if (this.num === 4) {
        this.num = 0;
      }
    },
    numTime() {
      this.timer = setInterval(this.numIncrease, 4000);
      // setInterval(() => {
      //   this.numIncrease;
      // }, 4000);
    },
    numChange(index) {
      this.num = index;
    },
  },
};
</script>

<style lang="scss" scoped>
.swiper-group {
  margin: auto;
  position: relative;
  width: 600px;
  height: 375px;
  overflow: hidden;
}
.img-enter-active {
  transition: all 1s ease;
  transform: translateX(0);
}
.img-leave-active {
  transition: all 1s ease;
  transform: translateX(-100%);
}
.img-enter {
  transform: translateX(100%);
}
.img-leave {
  transform: translateX(0);
}

.swiper-ul {
  list-style: none;

  li {
    position: absolute;
    // display: inline-block;
  }
}
.img {
  width: 600px;
}
.bar {
  span {
    display: inline-block;
    width: 10px;
    height: 10px;
    background: orange;
    border-radius: 10px;
    margin-right: 10px;
  }
  .active {
    background: red;
  }
}
</style>