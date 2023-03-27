<script>
import axios from 'axios';
import headerComp from './components/headerComp.vue';
import mainComp from './components/mainComp.vue';

export default {
  components: {
    headerComp,
    mainComp
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
