<script >
    import { store } from '../store.js';
    import CardComponent from '../components/CardComponent.vue'
    import AppLoader from './AppLoader.vue'

    export default {
        name: 'AppMain',
        components: {
            CardComponent,
            AppLoader
        },
        data() {
            return {
                store,
                values: ['Alien', 'Laval', 'Vylon', 'Inzektor', 'Umi', 'Gusto'],
                searchText: '',
                isLoading: true,
            }
        },

        methods: {
            stopLoader() {
                this.isLoading = false;
            }
        },
        created() {
            setTimeout(this.stopLoader, 2000);
        }
    }
</script>

<template>
    <AppLoader v-if="isLoading" />
    <section v-else>
        <div class="select-archetypes container">
        <select name="archetypes" id="choose-archetypes" @change="$emit('search', searchText)" v-model="searchText" >
            <option :value="value" v-for="value in values">
                {{ value }}
            </option>
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
    </section>
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