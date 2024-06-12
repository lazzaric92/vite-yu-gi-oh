<script>
import MainCardsList from './MainCardsList.vue';
import axios from 'axios';
import { store } from "../store.js";

export default{
    data(){
        return {
            store,
        }
    },
    methods: {
        getCardsList: function(){
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
            .then((response) => {
                this.store.cardsList = response.data.data;
                console.log(this.store.cardsList);
            })
            .catch(function (error) {
                // handle error
                console.log(error);
            })
            .finally(function () {
                // always executed
            });
        }
    },
    created(){
        this.getCardsList();
    },
    components: {
        MainCardsList
    }
}
</script>

<template>
    <main>
        <div class="container">
            <MainCardsList />
        </div>
    </main>
</template>

<style scoped lang="scss">
@use '../assets/styles/partials/variables' as *;
@use '../assets/styles/partials/mixins' as *;
    main {
        background-color: $bg-orange;
        padding: 4rem 0;
    }

    .container{
        @include my-container();
    }
</style>