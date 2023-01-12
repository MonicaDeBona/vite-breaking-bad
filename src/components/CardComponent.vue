<script>
export default{
    name: 'CardComponent',
    props: {
        card: Object,
    },
}
</script>

<template>
    <div class="card" :data-custom-id="card.id">
        <img :src="card.card_images[0].image_url" :alt="card.name">
        <h3>{{ card.name }}</h3>
        <h4>{{ card.archetype }}</h4>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/general.scss' as *;

.card {
    display: flex;
    flex-direction: column;
    width: calc((100% / 5) - 1rem);
    margin: 1rem .5rem;
    text-align: center;

    img {
        margin-bottom: .5rem;
        width: 100%;
    }

    h3 {
        text-transform: uppercase;
        padding-bottom: 1rem;
    }
}
</style>