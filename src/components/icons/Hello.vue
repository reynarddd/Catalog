<template>

    <nav class="bg-neutral-primary fixed w-full z-20 top-0 start-0 border-b border-default">
    <div class="w-full flex flex-wrap items-center p-4 justify-between">
    <a href="https://flowbite.com/" class="flex items-center space-x-3 rtl:space-x-reverse">
        <img src="https://flowbite.com/docs/images/logo.svg" class="h-7" alt="Flowbite Logo" />
        <span class="self-center text-xl text-heading font-semibold whitespace-nowrap">DummyJson*</span>
    </a>

    <form class="shadow-xs rounded-base -space-x-0.5 md:order-2 hidden md:flex">
        <div class="flex shadow-xs rounded-base -space-x-0.5">
            <label for="search-dropdown" class="block mb-2.5 text-sm font-medium text-heading sr-only ">Your Email</label>
            <button id="dropdown-button" data-dropdown-toggle="dropdown" type="button" class="inline-flex items-center shrink-0 z-10 text-body bg-neutral-secondary-medium box-border border border-default-medium hover:bg-neutral-tertiary-medium hover:text-heading focus:ring-4 focus:ring-neutral-tertiary font-medium leading-5 rounded-s-base text-sm px-4 py-2.5 focus:outline-none">
                <svg class="w-4 h-4 me-1.5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24"><path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.143 4H4.857A.857.857 0 0 0 4 4.857v4.286c0 .473.384.857.857.857h4.286A.857.857 0 0 0 10 9.143V4.857A.857.857 0 0 0 9.143 4Zm10 0h-4.286a.857.857 0 0 0-.857.857v4.286c0 .473.384.857.857.857h4.286A.857.857 0 0 0 20 9.143V4.857A.857.857 0 0 0 19.143 4Zm-10 10H4.857a.857.857 0 0 0-.857.857v4.286c0 .473.384.857.857.857h4.286a.857.857 0 0 0 .857-.857v-4.286A.857.857 0 0 0 9.143 14Zm10 0h-4.286a.857.857 0 0 0-.857.857v4.286c0 .473.384.857.857.857h4.286a.857.857 0 0 0 .857-.857v-4.286a.857.857 0 0 0-.857-.857Z"/></svg>
                All categories
                <svg class="w-4 h-4 ms-1.5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24"><path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m19 9-7 7-7-7"/></svg>
            </button>
            <div id="dropdown" class="z-10 hidden bg-neutral-primary-medium border border-default-medium rounded-base shadow-lg w-44">
                <ul class="p-2 text-sm text-body font-medium" aria-labelledby="dropdown-button">
                    <li v-for="lists in list">
                        <a @click="findCategory(lists)" href="#" class="block p-2 hover:bg-neutral-tertiary-medium hover:text-heading rounded-md">{{ lists }}</a>
                    </li>
                </ul>
            </div>
            <input @keydown.enter="search" v-model="search_value" type="search" id="search-dropdown input-group-1" class="px-3 py-2.5 bg-neutral-secondary-medium border border-default-medium text-heading text-sm focus:ring-brand focus:border-brand block w-full placeholder:text-body" placeholder="Search for products" required>
            <button @click="search" type="button" class="inline-flex items-center  text-white bg-brand hover:bg-brand-strong box-border border border-transparent focus:ring-4 focus:ring-brand-medium shadow-xs font-medium leading-5 rounded-e-base text-sm px-4 py-2.5 focus:outline-none">
            <svg class="w-4 h-4 me-1.5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24"><path stroke="currentColor" stroke-linecap="round" stroke-width="2" d="m21 21-3.5-3.5M17 10a7 7 0 1 1-14 0 7 7 0 0 1 14 0Z"/></svg>
            Search
            </button>
        </div>
    </form>

        <div class="items-center justify-between hidden w-full md:flex md:w-auto md:order-1" id="navbar-search">
        <div class="relative mt-3 md:hidden">
            <div class="absolute inset-y-0 start-0 flex items-center ps-3 pointer-events-none">
            <svg class="w-4 h-4 text-body" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24"><path stroke="currentColor" stroke-linecap="round" stroke-width="2" d="m21 21-3.5-3.5M17 10a7 7 0 1 1-14 0 7 7 0 0 1 14 0Z"/></svg>
            </div>
            <input type="text" id="input-group-1" class="block w-full ps-9 pe-3 py-2.5 bg-neutral-secondary-medium border border-default-medium text-heading text-sm rounded-base focus:ring-brand focus:border-brand px-2.5 py-2 shadow-xs placeholder:text-body" placeholder="Search">
        </div>
        <ul class="font-medium flex flex-col absolute p-4 md:p-0 mt-4 border border-default rounded-base bg-neutral-secondary-soft md:flex-row md:space-x-8 rtl:space-x-reverse md:mt-0 md:border-0 md:bg-neutral-primary">
            <li>
            <a href="#" class="block py-2 px-3 text-white bg-brand rounded md:bg-transparent md:text-fg-brand md:p-0" aria-current="page">Home</a>
            </li>
            <li>
            <a href="#" class="block py-2 px-3 text-heading rounded hover:bg-neutral-tertiary md:hover:bg-transparent md:border-0 md:hover:text-fg-brand md:p-0 md:dark:hover:bg-transparent">About</a>
            </li>
            <li>
            <a href="#" class="block py-2 px-3 text-heading rounded hover:bg-neutral-tertiary md:hover:bg-transparent md:border-0 md:hover:text-fg-brand md:p-0 md:dark:hover:bg-transparent">Services</a>
            </li>
        </ul>
        </div>
    </div>
    </nav>


    <div class="md:mt-28 mt-20">
        <h1 class="text-center my-8 text-4xl font-bold tracking-tight text-heading md:text-5xl lg:text-6xl">The project of DummyJson*!</h1>
        <p class="text-center my-8 text-lg font-normal text-body lg:text-xl sm:px-16 xl:px-48">Here at Flowbite we focus on markets where technology, innovation, and capital can unlock long-term value and drive economic growth.</p>
    </div>
    
    <hr></hr>  
    
    <div class="grid grid-cols-2 md:grid-cols-4 md:gap-x-14 max-w-screen md:px-20 md:mx-0 mx-3 gap-x-3 mt-5">
        <div v-for="product in products" class="flex items-center justify-center">
            <div class="bg-white block md:w-fit md:min-h-[700px] w-full min-h-[275px] md:p-6 p-3 border border-default rounded-base shadow-xs my-4 justify-center hover:scale-105 hover:drop-shadow-2xl transition-all">
                <a href="#">
                    <img class="rounded-base" :src="product?.thumbnail" alt="" />
                </a>
                <a href="#">
                    <h5 class="mt-6 mb-2 text-md md:text-2xl font-semibold tracking-tight text-black">{{product?.title || "Loading"}}</h5>
                </a>
                <p class="mb-6 text-black hidden md:block">{{product?.description || "Loading"}}</p>
                <br></br>
                <a :href="`/products/${ product?.id }`" class="inline-flex items-center text-body bg-neutral-secondary-medium box-border border border-default-medium hover:bg-neutral-tertiary-medium hover:text-heading focus:ring-4 focus:ring-neutral-tertiary shadow-xs font-medium leading-5 rounded-base text-sm px-4 py-2.5 focus:outline-none">
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
        this.categoryList()
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
        async categoryList(){
            const category = await axios.get(`https://dummyjson.com/products/category-list`);
            this.list = category.data
            console.log(category)
        },
        async findCategory(category){
            const result = await axios.get(`https://dummyjson.com/products/category/${category}`);
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
        },
    },
    data(){
        return {
            products : [],
            pagination : 1,
            query : '',
            search_value : '',
            list : '',
        }
    },

}

</script>