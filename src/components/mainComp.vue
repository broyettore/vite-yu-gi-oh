<script>
import searchComp from './searchComp.vue';
import cardContainer from './cardContainer.vue';

export default {
    name: "mainComponent",

    components: {
        searchComp,
        cardContainer
    }
}
</script>

<template>
    <main class="d-flex flex-column align-items-center justify-content-center py-5">
        <searchComp></searchComp>
        <cardContainer></cardContainer>
    </main>

</template>

<style lang="scss" scoped>
@use '../assets/styles/_partials/variables.scss' as *;
main {
    background-color: $bg-color;
    color: $primary-color;
}
</style>