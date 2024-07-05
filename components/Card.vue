<script setup lang="ts">

defineProps(['product'])

</script>

<template>
    <div class="card" style="width: 18rem;">
        <img :src="product.thumbnail" class="card-img-top" alt="...">

        <div class="card-body">
            <h5 class="card-title">{{ product.title }}</h5>
            <p class="card-text">{{ product.description }}</p>

            <NuxtLink :to="{ name: 'products-category-title', params: { title : product.title, category : product.category } }"
             class="btn btn-primary">
             Go somewhere
            </NuxtLink>
        </div>
    </div>
</template>