<template>
  <div class="tab-wrapper">
    <!-- 选项卡的头部 -->
    <header class="tab-head">
      <div class="tab-button" @click='current = 0' :class="{active:current===0}">最爱歌手</div>
      <div class="tab-button" @click='current = 1' :class="{ active: current === 1 }">最爱歌曲</div>
    </header>
    <div class="main">
      <div v-show="current===0">
        <!--球员-->
        <div class="tab-list">
          <tab-item :item="singer"/>
        </div>
      </div>
      <div v-show="current===1">
        <div class="tab-list">
          <tab-item :item="songs"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import {reactive,ref} from 'vue';
import TabItem from "./TabItem.vue";

let current = ref(0)
let singer = reactive({
  img:'/images/1.png',
  name:'黄霄雲',
  rate:1,
  alt:'黄霄雲',
  hot:433760
})
let songs=reactive({
  img:'/images/2021.jpg',
  name:'打开',
  rate:1,
  alt:'黄霄雲',
  hot:729858
})
</script>

<style scoped>
.tab-wrapper {
  width: 900px;
  margin: 100px auto;
  padding: 15px;
  background-color: rgb(45, 83, 211);
}

.tab-head {
  display: flex;
  border-radius: 10px;
  overflow: hidden;
}

.tab-button {
  flex: auto;
  background-color: #fff;
  padding: 10px 0;
  text-align: center;
  cursor: pointer;
  transition: .4s;
}

.tab-button:not(.active):hover {
  color: rgb(187, 3, 52);
}

.active {
  background-color: rgb(187, 3, 52);
}

.tab-list {
  margin: 10px;
}


</style>