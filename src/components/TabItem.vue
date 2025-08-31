<script setup>
const props = defineProps({
  item:{
    type: Object,
    required: true
  }
});
const {name,img,hot,rate}=props.item
</script>

<template>
  <div class="tab-item">
    <div class="tab-photo">
      <img :src='img' alt="黄霄雲">
      <span>{{rate}}</span>
    </div>
    <div class="tab-description">
      <div class="name">{{name}}</div>
      <div class="hot-bar">
        <div class="inner">{{hot}}热度</div>
      </div>
    </div>
  </div>

</template>

<style scoped>
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
  margin-left: 15px;
}

.tab-description .hot-bar {
  background-color: rgb(3, 37, 103);
  border-radius: 20px;
  text-indent: 0.5em;
}

.hot-bar .inner {
  background-color: darkred;
  border-radius: 20px;
  width: 40%;
  /*进度条颜色渐变*/
  background-image: linear-gradient(to right, rgb(187, 3, 52) 50%, rgb(66, 2, 12));
  white-space: nowrap;
}
</style>