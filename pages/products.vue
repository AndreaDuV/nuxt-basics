<script setup>
    //import {  products  } from '~/server/api/products.json';

    //const { data, error, pending } = await useFetch('https://dummyjson.com/products', {
    //    lazy: true,
    //    pick: ['products'],
    //});

    const { data, error, pending } = await useAsyncData('products', () => {
        return $fetch('https://dummyjson.com/products', {
            lazy: true,
            pick: ['products'],
        })
    })

</script>


<template>
    <div>
        <h1 v-if="pending">Loading data ...</h1>

        <div v-else>
            <h1>Page Products</h1>
            <div class="grid">
                <Card v-for="product in data.products" :key="product.id" :product="product"/>
            </div>
        </div>
        
    </div>
</template>

<style scoped>

.grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(18rem, 1fr));
    gap: 2rem;
}
</style>