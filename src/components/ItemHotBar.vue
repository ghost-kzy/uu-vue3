<template>
  <div class="hot-bar">
    <div class="inner">{{ hot }}热度</div>
  </div>

</template>

<script setup>
import {computed} from 'vue'

const {hot, maxHot} = defineProps({
  hot: {
    type: Number,
    default: 0
  },
  maxHot: {
    type: Number,
    default: 0
  }
})
const HotWidth = computed(() => {
  // return `${hot / maxHot}*100` + '%'
  return `${hot / maxHot * 100}%`
})
</script>

<style scoped>
.hot-bar {
  background-color: rgb(3, 37, 103);
  border-radius: 20px;
  text-indent: 0.5em;
}
.hot-bar .inner {
  background-color: darkred;
  border-radius: 20px;
  width: v-bind(HotWidth);
  /*进度条颜色渐变*/
  background-image: linear-gradient(to right, rgb(187, 3, 52) 50%, rgb(66, 2, 12));
  white-space: nowrap;
}
</style>