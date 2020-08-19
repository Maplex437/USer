<template>
  <div id="app">
    <ul class="demo">
      <li v-show="i===activeIndex" :v-for="(item,i) in imgList">
        <a href="#">
          <img :src="imgUrl" style="width:300px;height:170px;">
        </a>
      </li>
    </ul>
  </div>
</template>
 <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script>
// 不加载提示
Vue.config.devtools = true;
Vue.config.productionTip = false;

let vm = new Vue({
  el: "#app",
  data() {
    return {
      activeIndex: 0,
      imgList: [
        "@/assets/ninja640.jpg",
        "@/assets/ninja392.jpg",
        "@/assets/ninja854.jpeg",
      ],
    };
  },
  mounted() {
    setInterval(() => {
      if (++this.activeIndex === this.imgList.length) this.activeIndex = 0;
    }, 1000);
  },
});
</script>

<style>
</style>
