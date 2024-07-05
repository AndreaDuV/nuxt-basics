<script lang="ts" setup>

    const route = useRoute()

    definePageMeta({
        validate: (route) => {
            const regex = /^(?!\d*$)[a-zA-Z0-9]+(?:-[a-zA-Z0-9]+)*$/;
            const expression = new RegExp(regex);
            const title = String(route.params.title)
            return expression.test(title)
        }
    })

</script>

<template>
    <div>
        <h1>Ruta con Parámetros</h1>
        <h2>Parametro 1: {{ route.params.title }}</h2>
        <h2>Parametro 2: {{ route.params.category }}</h2>
    </div>
</template>