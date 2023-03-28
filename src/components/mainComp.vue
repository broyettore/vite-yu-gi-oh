<script>
import searchComp from './searchComp.vue';
import cardContainer from './cardContainer.vue';

export default {
    components: {
        searchComp,
        cardContainer
    },
    methods: {

        filterCard() {
            this.$emit("filterType")
        }
    }
}
</script>

<template>
    <main class="d-flex flex-column align-items-center justify-content-center py-5">
        <searchComp @filter="filterCard"></searchComp>
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