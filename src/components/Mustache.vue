<template>
  <div>
   <h2>当前用户：{{ username }}</h2>
    <p>2+3的结果是：{{ 2 + 3 }}</p>
  </div>
</template>

<script setup>
import { ref } from "vue";
const username = ref("张三");
console.log('111');
</script>

<style lang="scss" scoped></style>
