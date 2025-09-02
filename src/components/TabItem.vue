<script setup>
import Photo from "./Photo.vue";
import ItemHotBar from "./ItemHotBar.vue";

const  props = defineProps({
  item:{
    type: Object,
    required: true
  }
});
const {name,img,hot,rate,alt,maxHot}=props.item
</script>

<template>
  <div class="tab-item">
    <Photo :img="img" :rate='rate'  :alt="alt"/>
    <div class="tab-description">
      <div class="name">{{name}}</div>
      <ItemHotBar :hot="hot" :max-hot="maxHot"/>
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

.tab-description {
  flex: 1;
  display: flex;
  flex-flow: column;
  justify-content: space-evenly;
  /* background-color: salmon;*/
  margin-left: 15px;
}


</style>