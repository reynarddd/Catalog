<script setup>

import {ref, computed} from 'vue'
import Hello from './components/icons/Hello.vue';
import Single from './components/icons/Single.vue';

const routes = {
    "/" : Hello,
    "/products/:id" : Single,
}

const currentPath = ref(window.location.pathname)

window.addEventListener('hashchange', () => {
    currentPath.value = window.location.pathname
})

const productId = computed(() => {
    const path = currentPath.value
    
    if (path.startsWith("/products/")){
        return path.split('/')[2]
    }
    return null

})

const currentView = computed(() => {
    
    if (productId.value){
        return Single
    }
    return Hello
})

</script>

<template>
    <component :is="currentView" :productId="productId"/>
</template>