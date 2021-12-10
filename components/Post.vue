<template>
    <div>
        <nuxt-link to="/about">{{ item.name }}</nuxt-link>
        <p>{{ item.content }}</p>
    </div>
</template>

<script lang="ts">
export default({
    props: {
        item: {
            type: Object,
        }
    }
})
</script>