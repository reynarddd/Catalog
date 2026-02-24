<script setup>

import {ref, computed} from 'vue'
import Hello from './components/icons/Hello.vue';

const routes = {
    "/" : Hello
}

const currentPath = ref(window.location.hash)

window.addEventListener('hashchange', () => {
    currentPath.value = window.location.hash
})

const currentView = computed(() => {
    return routes[currentPath.value.slice(1) || '/'] || NotFound
})

</script>

<template>
    <a href="#/">Home</a>
    <component :is="currentView" />
</template>