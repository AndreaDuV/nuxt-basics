<script setup lang="ts">
    import {  products  } from '~/server/api/products.json'
</script>


<template>
    <div>
        <h1>Page Products</h1>
        <div class="grid">
            <Card v-for="product in products" :key="product.id" :="product"/>
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