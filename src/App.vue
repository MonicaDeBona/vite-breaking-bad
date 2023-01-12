<script >
import axios from "axios";
import { store } from "./store.js";
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';


export default {

  data() {
    return {
      store,
      apiUrl:'https://db.ygoprodeck.com/api/v7/cardinfo.php?',
      currentArchetypes: 'alien'
    }
  },

  components: {
    AppHeader,
    AppMain
  },

  methods: {
    getCardElement(searchArchetypes) {
      axios.get(this.apiUrl, {
        params: {
          archetype: searchArchetypes,
          num: 10,
          offset: 0

        }
      })
      .then((response) => {
          this.store.cardsList = response.data.data;
      })
    }
  },

  created() {
    this.getCardElement(this.currentArchetypes);
  }
}
</script>

<template>

  <header>
    <AppHeader />
  </header>

  <main>
    <AppMain @search="getCardElement"/>
  </main>

</template>

<style lang="scss">
@use './styles/general.scss' as *;
@use './styles/partials/variables.scss' as *;
// @use '../node_modules/bootstrap/scss/bootstrap.scss' as *;
</style>
