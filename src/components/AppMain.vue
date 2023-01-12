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
        <div class="card-found">
            <p>Found {{ store.cardsList.length }} cards</p>
        </div>
        <div class="card-container">
            <CardComponent v-for="cardElement in store.cardsList" 
            :card="cardElement"/>
        </div>
    </div>
</template>

<style lang="scss" scoped>

    .container {
        width: 55%;
        margin: 0 auto;

        .card-found {
            padding: 1rem;
            text-align: center;
            background-color: black;
            color: white;
            text-transform: uppercase;
        }
    }
    .card-container {
        display: flex;
        flex-wrap: wrap;  
        background-color: bisque;  
        padding: 2rem;
    }
</style>