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
  created() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php') 
    .then((response) => {
      this.store.cards = response.data.data;
      this.store.limitedCards = this.store.cards.slice(0, 50).length;
    })
  }
}
</script>

<template>
  <headerComp></headerComp>
  <mainComp></mainComp>
</template>

<style lang="scss" scoped>
@use './assets/styles/_partials/variables.scss'
</style>
