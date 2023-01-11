<script >
import axios from "axios";
import { store } from "./store.js";
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';


export default {

  data() {
    return {
      store,
    }
  },

  components: {
    AppHeader,
    AppMain
  },

  methods: {
    getCardElement() {
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0', {
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

  <header>
    <AppHeader />
  </header>

  <main>
    <AppMain />
  </main>

</template>

<style lang="scss">
@use './styles/general.scss' as *;
@use './styles/partials/variables.scss' as *;
@use '../node_modules/bootstrap/scss/bootstrap.scss' as *;
</style>
