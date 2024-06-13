<script>
import axios from 'axios';
import { store } from "../store.js";

export default{
    data(){
        return {
            store,
        }
    },
    methods: {
        getArchetypes: function(){
            axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
            .then((response) => {
                this.store.archetypes = response.data;
                console.log(this.store.archetypes);
            })
            .catch(function (error) {
                console.log(error);
            });  
        }
    },
    created(){
        this.getArchetypes();
    }
}
</script>

<template>
    <div class="container">
        <select id="archetypes-select">
            <option v-for="(archetype, index) in store.archetypes" :key="archetype.index" :value="archetype.archetype_name"> {{ archetype.archetype_name }} </option>
        </select>
    </div>
</template>

<style scoped lang="scss">
    @use '../assets/styles/partials/variables' as *;
    @use '../assets/styles/partials/mixins' as *;

    .container {
        @include my-container();
        padding: 1rem;
        margin-bottom: 1rem;

        select {
            padding: .4rem .6rem;
        }
    }
</style>