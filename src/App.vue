<script>
import axios from 'axios';
import { store } from './store';
import headerComp from './components/headerComp.vue';
import mainComp from './components/mainComp.vue';

export default {
  data() {
    return {
      store
    }
  },
  components: {
    headerComp,
    mainComp
  },
  methods: {

    search() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php', {
        params: {
          archetype: store.searchSelect,
        }
      }) 
    .then((response) => {
      this.store.cards = response.data.data;
      this.store.limitedCards = this.store.cards.slice(0, 1000).length;
      this.store.loading = false;
    })
    .catch((error) => {
        console.log(error);
        this.store.cards = [];
        this.store.limitedCards = 0;
      })
  },
  created() {
    this.search();
  }

  }
}
</script>

<template>
  <headerComp></headerComp>
  <mainComp @filterType="search"></mainComp>
</template>

<style lang="scss" scoped>
@use './assets/styles/_partials/variables.scss'
</style>
