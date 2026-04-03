<template>
<!-- <p>{{ product }}</p> -->
    <div class="flex justify-center">
        <div class="w-[500px] h-[500px]">
            <img class="rounded-base" :src="product?.images" alt="" />
            
            <p class="text-2xl mb-5">Description</p>
            <p class="mt-5 mb-3">{{ product?.description }}</p>
            <p class="mb-3">Category : {{ product?.category }} product</p>
            <p class="mb-3">SKU : {{ product?.sku }}</p>

        </div>
        <div class="w-[500px] h-[500px]">
            <p class="mt-10 mb-7">{{ product?.title }}</p>
            
            <p class="text-3xl mb-7">$ {{ product?.price }}</p>
            <div class="flex items-center">
                <p class="text-xs mr-3">{{ product?.availabilityStatus }}</p>
                
                <div class="flex items-center">
                    <svg class="w-5 h-5 text-fg-yellow" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="currentColor" viewBox="0 0 24 24"><path d="M13.849 4.22c-.684-1.626-3.014-1.626-3.698 0L8.397 8.387l-4.552.361c-1.775.14-2.495 2.331-1.142 3.477l3.468 2.937-1.06 4.392c-.413 1.713 1.472 3.067 2.992 2.149L12 19.35l3.897 2.354c1.52.918 3.405-.436 2.992-2.15l-1.06-4.39 3.468-2.938c1.353-1.146.633-3.336-1.142-3.477l-4.552-.36-1.754-4.17Z"/></svg>
                    <p class="ms-2 text-sm font-bold text-heading">{{ product?.rating }}</p>
                    <span class="w-1 h-1 mx-1.5 bg-neutral-quaternary rounded-full"></span>
                    <a href="#" class="text-sm font-medium text-heading underline hover:no-underline">{{ product?.reviews.length}} reviews</a>
                </div>
            </div>
        </div>
        
    </div>
</template>

<script>

import axios from 'axios';

export default{
    props: ['productId'],
    data(){
        return {
            product : null
        }
    },
    mounted(){
        this.fetchapi()
    },
    watch: {
        productId(){
            this.fetchapi()
        },
    },
    methods:{
        async fetchapi(){
            const result = await axios.get(`https://dummyjson.com/products/${this.productId}`);
            this.product = result.data
            console.log(result)
        },
    }
}

</script>