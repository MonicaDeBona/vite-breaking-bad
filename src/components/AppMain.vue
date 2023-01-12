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
                values: ['Alien', 'Laval', 'Vylon', 'Inzektor', 'Umi', 'Gusto'],
                searchText: ''
            }
        },
    }
</script>

<template>




    <div class="select-archetypes container">
        <select name="archetypes" id="choose-archetypes" @change="$emit('search', searchText)" v-model="searchText" >
            <option value="alien">Alien</option>
            <option value="laval">Laval</option>
            <option value="vylon">Vylon</option>
            <option value="inzektor">Inzektor</option>
            <option value="umi">Umi</option>
            <option value="gusto">Gusto</option>
        </select>
    </div>






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

    #choose-archetypes {
        padding: .5rem 3rem;
        margin: 1rem 0;
    }
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