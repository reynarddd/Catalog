<script setup>
import { onMounted } from 'vue'
import { initFlowbite } from 'flowbite'
onMounted(() => {
    initFlowbite();
})

import Router from './Router.vue';
</script>


<template>
<Router/>
</template>


<style scoped>


</style>