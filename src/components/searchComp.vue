<script>
import axios from 'axios';
import { store } from '../store';
export default {
    data() {
        return {
            store
        }
    },
    created() {

        axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then((response) => {
            this.store.archetypes = response.data;
            console.log(this.store.archetypes[1].archetype_name)
        })
    }
}
</script>

<template>
    <div class="container mb-3">
        <select class="form-select ms-select" aria-label="Default select example" v-model="store.searchSelect" @change="$emit('filter')">
            <option value="" selected>Select type</option>
            <option :value="archetype.archetype_name" v-for="archetype in store.archetypes">{{ archetype.archetype_name }}</option>
    </select>
    </div>
</template>

<style lang="scss" scoped>

.ms-select {
    width: 20%;
}
</style>