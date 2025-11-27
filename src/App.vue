<script setup>
import { onMounted } from 'vue'
import { initFlowbite } from 'flowbite'
onMounted(() => {
    initFlowbite();
})


import Hello from './components/icons/Hello.vue';
</script>


<template>
<Hello/>
</template>


<style scoped>


</style>