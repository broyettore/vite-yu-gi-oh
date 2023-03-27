<script>
import cardComp from './cardComp.vue';

export default {
    components: {
        cardComp
    }
}
</script>

<template>
    <div class="container d-flex justify-content-center align-items-center p-5">
        <div class="card-ctn">
            <div class="card-filter p-3">
                <span>Found</span>
            </div>
            <div class="card-list">
                <cardComp></cardComp>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../assets/styles/_partials/variables.scss' as *;
.container {
    background-color: $primary-color;
    color: $primary-color;
    height: 90%;

    .card-ctn {
        width: 100%;
        height: 100%;
        background-color: #212529;
    }
}
</style>