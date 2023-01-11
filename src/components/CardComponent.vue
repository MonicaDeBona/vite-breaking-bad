<script>
export default{
    name: 'CardComponent',
    props: {
        card: Object,
    },
}
</script>

<template>
    <article class="single-card" :data-custom-id="card.id">
        <img :src="card.card_images[0].image_url" :alt="card.name">
        <h3>{{ card.name }}</h3>
    </article>
</template>

<style lang="scss" scoped>
</style>