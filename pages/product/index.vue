<template>
    <div>
        <header class="shadow-sm bg-white"> 
            <nav class="container mx-auto p-4 flex justify-between">
                <NuxtLink to="/" class="font-bold">Nuxt Dojo</NuxtLink>
                <ul class="flex gap-4">
                    <li><NuxtLink to="/">Home</NuxtLink></li>
                    <li><NuxtLink to="/product">Products</NuxtLink></li>
                </ul>
            </nav>
        </header>
        <div class="grid grid-cols-3 gap-5">
            <div v-for="(x, index) in products" :key="index" class="flex=center pl-20 pr-20 pb-20 pt-20">



<NuxtLink :to="`/products/${x.id}`"> 

    <img class="h-28 w-28 border-black bg-gray-300" :src="x.image" alt="Product Image">

</NuxtLink>

<br>

<NuxtLink :to="`/products/${x.id}`">

    Title: {{ x.title }}

</NuxtLink>

<br>

<NuxtLink :to="`/products/${x.id}`">

    Price: {{ x.price }}

</NuxtLink>

<br>

<NuxtLink :to="`/products/${x.id}`">

    Category: {{ x.category }}

</NuxtLink>



</div>
        
        </div>
    </div>
</template>

<script setup>
definePageMeta({
    layout: 'Products'
})

const {data: products } = await useFetch('https://fakestoreapi.com/products')

</script>

<style scoped>

</style>