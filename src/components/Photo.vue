<script setup>
import {computed} from "vue";

const {img,rate,alt}=defineProps({
  img: {
    type: String,
    required: true
  },
  rate: {
    type: Number,
    required: true
  },
  alt: {
    type: String,
    required: true
  }
})
const Color=computed(()=>{
  if(rate==1){
    return 'rgb(245, 102, 1)'
  }
  else if(rate==2){
    return 'rgb(45, 180, 1)'
  }
  else if(rate==3){
    return 'rgb(245, 240, 1)'
  }else{
    return 'rgb(145, 2, 1)'
  }
})

</script>

<template>
  <div class="tab-photo">
    <img :src='img' :alt="alt">
    <span>{{rate}}</span>
  </div>
</template>

<style scoped>
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
  background-color: v-bind(Color);
  border-radius: 0 0 15px 0;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>