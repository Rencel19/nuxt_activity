<template>
    <div>
        <p>Product details for {{ id }}</p>

        <p>{{ product.title }}</p>
        <p>{{ product.price }}</p>
        <p>{{ product.id }}</p>
    </div>
</template>

<script setup>

const { id } = useRoute().params
const uri = 'https://fakestoreapi.com/products' + id


const {data: products } = await useFetch(uri, {key: id })

</script>

<style scoped>

</style>