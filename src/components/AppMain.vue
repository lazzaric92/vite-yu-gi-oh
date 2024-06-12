<script>
import MainCardsList from './MainCardsList.vue';
import axios from 'axios';
import { store } from "../store.js";

export default{
    data(){
        return {
            message: 'Main',
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
    <h1> {{ message }} </h1>
    <MainCardsList />
</template>

<style scoped lang="scss">

</style>