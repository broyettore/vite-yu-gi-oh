<script>
import logo from './logo.vue';

export default {
    data() {
        return {
            name: "headerComponent",
        }
    },
    components: {
        logo
    }
}
</script>

<template>
    <header>
        <div class="container-fluid p-2 d-flex align-items-center">
            <logo></logo>
            <h1 class="fs-2">Yu-Gi-Oh Api</h1>
        </div>
    </header>
</template>

<style lang="scss" scoped>
h1 {
    margin: 0;
}
</style>