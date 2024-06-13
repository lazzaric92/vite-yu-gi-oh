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
            isLoaded: true,
        }
    },
    methods: {
        // getCardsList: function(){
        //     axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=40&offset=0')
        //     .then((response) => {
        //         this.store.cardsList = response.data.data;
        //         console.log(this.store.cardsList);
        //     })
        //     .catch(function (error) {
        //         // handle error
        //         console.log(error);
        //     });
        // },
        loadingFunction: function(){
            setTimeout(() => {
                this.isLoaded = true;
            }, 3000);
        },
        getCardsByArchetypes: function(value){
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php', {
                params: {
                    archetype: value
                }
            })
            .then((response) => {
                this.store.cardsList = response.data;
                console.log(this.store.cardsList);
            })
            .catch(function (error) {
                console.log(error);
            });  
        }
    },
    created(){
        // this.loadingFunction();
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
            <MainCardsList v-if="isLoaded" />
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