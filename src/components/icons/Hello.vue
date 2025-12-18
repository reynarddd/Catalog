<template>
    <div class="grid grid-cols-4 gap-2 w-screen">
        <div v-for="product in products">
            <div class="bg-[#050E3C] block max-w-sm p-6 border border-default rounded-base shadow-xs">
                <a href="#">
                    <img class="rounded-base" :src="product?.thumbnail" alt="" />
                </a>
                <a href="#">
                    <h5 class="mt-6 mb-2 text-2xl font-semibold tracking-tight text-heading">{{product?.title || "Loading"}}</h5>
                </a>
                <p class="mb-6 text-body">{{product?.description || "Loading"}}</p>
                <br></br>
                <a href="#" class="inline-flex items-center text-body bg-neutral-secondary-medium box-border border border-default-medium hover:bg-neutral-tertiary-medium hover:text-heading focus:ring-4 focus:ring-neutral-tertiary shadow-xs font-medium leading-5 rounded-base text-sm px-4 py-2.5 focus:outline-none">
                    Read more
                    <svg class="w-4 h-4 ms-1.5 rtl:rotate-180 -me-0.5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24"><path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 12H5m14 0-4 4m4-4-4-4"/></svg>
                </a>
            </div>
        </div>
    </div>


</template>

<script>
import axios from 'axios';

export default{
    mounted(){
        this.fetchapi()
    },
    methods:{
        async fetchapi(){
            const result = await axios.get('https://dummyjson.com/products');
            this.products = result.data.products
            console.log(result)
        }
    },
    data(){
        return {
            products : []
        }
    }
}

</script>