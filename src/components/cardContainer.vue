<script>
import { store } from '../store';
import cardComp from './cardComp.vue';

export default {
    data() {
        return {
            store,
        }
    },
    components: {
        cardComp
    },
}
</script>

<template>
    <div class="container d-flex justify-content-center align-items-center p-5">
        <div class="card-ctn">
            <div class="card-filter p-3">
                <span>Found {{ store.limitedCards }} cards</span>
            </div>
            <div class="loader-ctn d-flex justify-content-center p-3" v-show="store.limitedCards === 0">
                <div class="loader"></div>
            </div>
            <div class="row row-cols-1 row-cols-md-3 row-cols-lg-5 gy-2">
                <div class="col d-flex align-items-stretch"  v-for="(card, index) in store.cards.slice(0, 1000)">
                    <cardComp :img="card.card_images[0].image_url"  :name="card.name.toUpperCase()" :species="card.archetype"/>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../assets/styles/_partials/variables.scss' as *;
.container {
    background-color: $primary-color;
    color: $primary-color;

    .card-ctn,
    .loader-ctn {
        width: 100%;

        .card-filter {
            background-color: #212529;
        }

        .loader {
                display: block;
                width: 64px;
                height: 64px;
                margin: 8px;
                border-radius: 50%;
                border: 6px solid #000;
                border-color: #000 transparent #000 transparent;
                animation: loader 1.2s linear infinite;
        }
                @keyframes loader {
                0% {
                    transform: rotate(0deg);
                }
                100% {
                    transform: rotate(360deg);
                }
                }
    }  
}
</style>