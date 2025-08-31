<template>
  <div class="tab-wrapper">
    <!-- 选项卡的头部 -->
    <header class="tab-head">
      <div class="tab-button" @click='current = 0' :class="{active:current===0}">热门球员</div>
      <div class="tab-button" @click='current = 1' :class="{ active: current === 1 }">热门球队</div>
    </header>
    <div class="main">
      <div v-show="current===0">
        <!--球员-->
        <div class="tab-list">
          <div class="tab-item">
            <div class="tab-photo">
              <img src="/public/images/messi.png" alt="梅西">
              <span>1</span>
            </div>
            <div class="tab-description">
              <div class="name">梅西</div>
              <div class="hot-bar">
                <div class="inner">433760热度</div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div v-show="current===1">
        <div class="tab-list">
          <div class="tab-item">
            <div class="tab-photo">
              <img src="/public/images/法国.jpg" alt="法国">
              <span>1</span>
            </div>
            <div class="tab-description">
              <div class="name">法国</div>
              <div class="hot-bar">
                <div class="inner">433760热度</div>
              </div>
            </div>
          </div>

        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import {ref} from 'vue';

let current = ref(0)

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

.tab-item {
  display: flex;
  margin-bottom: 20px;
  color: #ffffff;
  font-size: 20px;
}

.tab-photo {
  width: 150px;
  background-color: #fff;
  border-radius: 20px;
  overflow: hidden;
  position: relative;
}

.tab-photo img {
  width: 100%;
  vertical-align: middle;
}

.tab-photo span {
  position: absolute;
  top: 0;
  left: 0;
  width: 30px;
  height: 30px;
  font-weight: bold;
  font-size: 22px;
  background-color: rgb(245, 102, 1);
  border-radius: 0 0 15px 0;
  display: flex;
  justify-content: center;
  align-items: center;
}

.tab-description {
  flex: 1;
  display: flex;
  flex-flow: column;
  justify-content: space-evenly;
 /* background-color: salmon;*/
  margin-left:  15px;
}
.tab-description .hot-bar {
  background-color: rgb(3,37,103);
  border-radius: 20px;
  text-indent: 0.5em;
}
.hot-bar .inner{
  background-color: darkred;
  border-radius: 20px;
  width: 40%;
  /*进度条颜色渐变*/
  background-image: linear-gradient(to right, rgb(187,3,52) 50%, rgb(66,2,12));
  white-space: nowrap;
}
</style>