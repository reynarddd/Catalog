<template>
    
    <div class="">
        <h1 class="text-center my-8 text-4xl font-bold tracking-tight text-heading md:text-5xl lg:text-6xl">We invest in the world’s potential</h1>
        <p class="text-center my-8 text-lg font-normal text-body lg:text-xl sm:px-16 xl:px-48">Here at Flowbite we focus on markets where technology, innovation, and capital can unlock long-term value and drive economic growth.</p>
    </div>
    
    <hr></hr>

    <form class="max-w-2xl mx-auto my-5">
        <div class="flex shadow-xs rounded-base -space-x-0.5">
            <label for="search-dropdown" class="block mb-2.5 text-sm font-medium text-heading sr-only ">Your Email</label>
            <button id="dropdown-button" data-dropdown-toggle="dropdown" type="button" class="inline-flex items-center shrink-0 z-10 text-body bg-neutral-secondary-medium box-border border border-default-medium hover:bg-neutral-tertiary-medium hover:text-heading focus:ring-4 focus:ring-neutral-tertiary font-medium leading-5 rounded-s-base text-sm px-4 py-2.5 focus:outline-none">
                <svg class="w-4 h-4 me-1.5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24"><path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.143 4H4.857A.857.857 0 0 0 4 4.857v4.286c0 .473.384.857.857.857h4.286A.857.857 0 0 0 10 9.143V4.857A.857.857 0 0 0 9.143 4Zm10 0h-4.286a.857.857 0 0 0-.857.857v4.286c0 .473.384.857.857.857h4.286A.857.857 0 0 0 20 9.143V4.857A.857.857 0 0 0 19.143 4Zm-10 10H4.857a.857.857 0 0 0-.857.857v4.286c0 .473.384.857.857.857h4.286a.857.857 0 0 0 .857-.857v-4.286A.857.857 0 0 0 9.143 14Zm10 0h-4.286a.857.857 0 0 0-.857.857v4.286c0 .473.384.857.857.857h4.286a.857.857 0 0 0 .857-.857v-4.286a.857.857 0 0 0-.857-.857Z"/></svg>
                All categories
                <svg class="w-4 h-4 ms-1.5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24"><path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m19 9-7 7-7-7"/></svg>
            </button>
            <div id="dropdown" class="z-10 hidden bg-neutral-primary-medium border border-default-medium rounded-base shadow-lg w-44">
                <ul class="p-2 text-sm text-body font-medium" aria-labelledby="dropdown-button">
                    <li>
                        <a href="#" class="block p-2 hover:bg-neutral-tertiary-medium hover:text-heading rounded-md">Shopping</a>
                    </li>
                    <li>
                        <a href="#" class="block p-2 hover:bg-neutral-tertiary-medium hover:text-heading rounded-md">Images</a>
                    </li>
                    <li>
                        <a href="#" class="block p-2 hover:bg-neutral-tertiary-medium hover:text-heading rounded-md">News</a>
                    </li>
                    <li>
                        <a href="#" class="block p-2 hover:bg-neutral-tertiary-medium hover:text-heading rounded-md">Finance</a>
                    </li>
                </ul>
            </div>
            <input v-model="search_value" type="search" id="search-dropdown input-group-1" class="px-3 py-2.5 bg-neutral-secondary-medium border border-default-medium text-heading text-sm focus:ring-brand focus:border-brand block w-full placeholder:text-body" placeholder="Search for products" required>
            <button @click="search" type="button" class="inline-flex items-center  text-white bg-brand hover:bg-brand-strong box-border border border-transparent focus:ring-4 focus:ring-brand-medium shadow-xs font-medium leading-5 rounded-e-base text-sm px-4 py-2.5 focus:outline-none">
            <svg class="w-4 h-4 me-1.5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24"><path stroke="currentColor" stroke-linecap="round" stroke-width="2" d="m21 21-3.5-3.5M17 10a7 7 0 1 1-14 0 7 7 0 0 1 14 0Z"/></svg>
            Search
            </button>
        </div>
    </form>


    
    
    
    <div class="grid grid-cols-4 gap-2 w-screen mx-7">
        <div v-for="product in products">
            <div class="bg-white block max-w-sm min-h-[650px] p-6 border border-default rounded-base shadow-xs my-5">
                <a href="#">
                    <img class="rounded-base" :src="product?.thumbnail" alt="" />
                </a>
                <a href="#">
                    <h5 class="mt-6 mb-2 text-2xl font-semibold tracking-tight text-black">{{product?.title || "Loading"}}</h5>
                </a>
                <p class="mb-6 text-black">{{product?.description || "Loading"}}</p>
                <br></br>
                <a href="#" class="inline-flex items-center text-body bg-neutral-secondary-medium box-border border border-default-medium hover:bg-neutral-tertiary-medium hover:text-heading focus:ring-4 focus:ring-neutral-tertiary shadow-xs font-medium leading-5 rounded-base text-sm px-4 py-2.5 focus:outline-none">
                    Read more
                    <svg class="w-4 h-4 ms-1.5 rtl:rotate-180 -me-0.5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24"><path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 12H5m14 0-4 4m4-4-4-4"/></svg>
                </a>
            </div>
        </div>
    </div>



    <nav aria-label="Page navigation example" class="flex justify-center my-5">
        <ul class="flex -space-x-px text-sm">
            <li>
            <a @click="prev" :class="pagination > 1 ? 'flex' : 'hidden'" class="items-center justify-center text-body bg-neutral-secondary-medium box-border border border-default-medium hover:bg-neutral-tertiary-medium hover:text-heading font-medium rounded-s-base text-sm w-9 h-9 focus:outline-none">
                <span class="sr-only">Previous</span>
                <svg class="w-4 h-4 rtl:rotate-180" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24"><path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m15 19-7-7 7-7"/></svg>
            </a>
            </li>
            <div v-for="index in 6">
                <div v-if="pagination > 6">
                    <li>
                        <a @click="goTo(index + (pagination - 6))" :class="pagination == index + (pagination - 6) ? 'bg-neutral-tertiary hover:text-fg-brand text-fg-brand' : 'bg-neutral-secondary-medium hover:text-heading  text-body'" class="flex items-center justify-center   box-border border border-default-medium hover:bg-neutral-tertiary-medium font-medium text-sm w-9 h-9 focus:outline-none">{{index + (pagination - 6) }}</a>
                    </li>
                </div>
                <div v-else>
                    <li>
                        <a @click="goTo(index)" :class="pagination == index ? 'bg-neutral-tertiary hover:text-fg-brand text-fg-brand' : 'bg-neutral-secondary-medium hover:text-heading  text-body'" class="flex items-center justify-center   box-border border border-default-medium hover:bg-neutral-tertiary-medium font-medium text-sm w-9 h-9 focus:outline-none">{{index }}</a>
                    </li>
                </div>
            </div>
            <li>
            <a @click="next" class="flex items-center justify-center text-body bg-neutral-secondary-medium box-border border border-default-medium hover:bg-neutral-tertiary-medium hover:text-heading font-medium rounded-e-base text-sm w-9 h-9 focus:outline-none">
                <span class="sr-only">Next</span>
                <svg class="w-4 h-4 rtl:rotate-180" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24"><path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m9 5 7 7-7 7"/></svg>
            </a>
            </li>
        </ul>
    </nav>

</template>

<script>
import axios from 'axios';

export default{
    mounted(){
        this.fetchapi()
    },
    methods:{
        async fetchapi(){
            const result = await axios.get(`https://dummyjson.com/products?limit=12&skip=${(this.pagination -1) * 10}`);
            this.products = result.data.products
            console.log(result) 
        },
        async search(){
            const result = await axios.get(`https://dummyjson.com/products/search?q=${this.search_value}`);
            this.products = result.data.products
            console.log(this.products)
        },
        next(){
            this.pagination += 1
            this.fetchapi()
        },
        prev(){
            if(this.pagination > 1){
                this.pagination -= 1
                this.fetchapi()
            }
        },
        goTo(num){
            this.pagination = num
            this.fetchapi()

        }
    },
    data(){
        return {
            products : [],
            pagination : 1,
            query : '',
            search_value : '',
        }
    },
}

</script>