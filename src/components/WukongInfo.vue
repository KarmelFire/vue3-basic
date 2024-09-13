<template>
    <div>
        <h2>{{ name }}</h2>
        <h3>{{ title }}</h3>
        <h3>{{ description }}</h3>
    </div>
</template>

<script setup lang="ts">
import {ref} from 'vue'
const name = ref<string>('孙悟空')
const title = ref<string>('斗战胜佛')
const description = ref<string>('孙悟空是中国古典小说《西游记》中的主要角色之一，由石生，后拜唐僧为师，是唐僧的大徒弟。他以机智、勇敢、忠诚著称，拥有七十二变和筋斗云等神通，保护唐僧西天取经。')
</script>

<style scoped>
h2,h3{
    font-weight: bold;
}
div{
    background-color: #7cc4d9;
}
</style>