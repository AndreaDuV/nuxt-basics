<script setup lang="ts">

defineProps({
    title: String,
    slug: String,
    description: String,
    thumbnail: String,
    category: String,
})

</script>

<template>
    <div class="card" style="width: 18rem;">
        <img :src="thumbnail" class="card-img-top" alt="...">

        <div class="card-body">
            <h5 class="card-title">{{ title }}</h5>
            <p class="card-text">{{ description }}</p>

            <NuxtLink :to="{ name: 'products-category-title', params: { title : slug, category } }"
             class="btn btn-primary">
             Go somewhere
            </NuxtLink>
        </div>
    </div>
</template>