<template>
  <div>
    <reduce></reduce>
    <url2></url2>
    <vmodel></vmodel>
    <div class="container">
      <div class="imglist">
        <h3>图片列表区</h3>
        <img
          src="./assets/01.jpg"
          alt=""
          @mouseover="mouseoverFn(1)"
          @click="clickFn(1, $event)"
        />
        <img
          src="./assets/02.jpg"
          alt=""
          @mouseover="mouseoverFn(2)"
          @click="clickFn(2, $event)"
        />
        <img
          src="./assets/03.jpg"
          alt=""
          @mouseover="mouseoverFn(3)"
          @click="clickFn(3, $event)"
        />
      </div>
      <div class="show">
        <h3>图片预览区</h3>
        <img :src="imgUrl" alt="" style="width: 600px; height: auto" />
      </div>
    </div>
  </div>
</template>

<script>
import reduce from './components/3.reduce.vue'
import url2 from './components/2.url.vue'
import vmodel from './components/1.v-model.vue'
import img01 from './assets/01.jpg'
import img02 from './assets/02.jpg'
import img03 from './assets/03.jpg'
export default {
  components: {
    reduce,
    url2,
    vmodel,
  },
  data() {
    return {
      imgUrl: img01,
    }
  },
  methods: {
    mouseoverFn(val) {
      this.imgUrl = { 1: img01, 2: img02, 3: img03 }[val]
    },
    clickFn(val, e) {
      alert(e.target.src)
    },
  },
}
</script>

<style scoped>
.container {
  display: flex;
}
.imglist {
  border: 2px solid red;
}
.imglist img {
  width: 200px;
  height: auto;
}
.show {
  border: 2px solid red;
  margin-right: 20px;
}
</style>
