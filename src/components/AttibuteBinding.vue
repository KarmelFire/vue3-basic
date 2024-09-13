<template>
    <div>
        <button :disabled="isDisabled">点击</button>
        <img :src="url">
    </div>
</template>

<script setup lang="ts">
import {ref} from 'vue'
const isDisabled = ref<boolean>(false)
const url = ref<string>('https://web.sanguosha.com/10/pc/res/assets/runtime/general/big/static/551703.png?v=c142f04e1')
</script>
