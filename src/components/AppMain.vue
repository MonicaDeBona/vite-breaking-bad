<script >
    import CardComponent from '../components/CardComponent.vue'
    import { store } from '../store.js';
    

    export default {
        name: 'AppMain',
        components: {
            CardComponent,
        },
        data() {
            return {
                store,
            }
        },
    }
</script>

<template>
    <div class="container">
        <CardComponent v-for="cardElement in store.cardsList" 
        :card="cardElement"/>
    </div>
</template>

<style lang="scss" scoped>

</style>