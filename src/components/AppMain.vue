<script>
import AppSearch from './AppSearch.vue';
import MainCardsList from './MainCardsList.vue';
import MainLoader from './MainLoader.vue';
import axios from 'axios';
import { store } from "../store.js";

export default{
    data(){
        return {
            store,
            isLoading: false,
        }
    },
    methods: {
        loadingFunction: function(){
            setTimeout(() => {
                this.isLoading = false;
            }, 2000);
        },
        getCardsByArchetypes: function(value){
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php', {
                params: {
                    archetype: value
                }
            })
            .then((response) => {
                this.isLoading = true;
                this.store.cardsList = response.data.data;
                this.loadingFunction();
            })
            .catch(function (error) {
                console.log(error);
            });  
        }
    },
    components: {
        AppSearch,
        MainCardsList,
        MainLoader
    }
}
</script>

<template>
    <main>
        <div class="container">
            <AppSearch @search="getCardsByArchetypes" />
            <MainCardsList v-if="(!isLoading)" />
            <MainLoader v-else />
        </div>
    </main>
</template>

<style scoped lang="scss">
@use '../assets/styles/partials/variables' as *;
@use '../assets/styles/partials/mixins' as *;

    .container{
        @include my-container();
    }
</style>