<template>
  <h3>{{ msg }}</h3>
  <div v-html="html"></div>
  <div>{{html}}</div>
</template>
<script setup>
import { ref } from "vue";

const msg = ref('孔中由')
const html = `<h2>我是一段HTML代码</h2>`

</script>

<style scoped></style>