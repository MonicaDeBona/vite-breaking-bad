<script >
    import { store } from '../store.js';
    import axios from 'axios';

    export default {
        name: 'AppMain',
        data() {
            return {
                store,
                apiCardList: ' https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0'
            }
        },
        methods: {
            getCardElement() {
                //dentro recupero tramite ajax le carte
                axios.get(this.apiCardList, {
                    params: {

                    }
                })
                .then((response) => {
                    this.store.cardsList = response.data.data;
                })
            }
        },

        created() {
            this.getCardElement();
        }
    }
</script>

<template>
    <h2>Main</h2>
</template>

<style lang="scss" scoped>

</style>