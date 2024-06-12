<script>
import MainSingleCard from './MainSingleCard.vue';
import { store } from "../store.js";

export default{
    data(){
        return {
            message: 'Here\'s the cards',
            store,
        }
    },
    components: {
        MainSingleCard
    }
}
</script>

<template>
    <h1> {{ message }} </h1>
    <MainSingleCard v-for="card in store.cardsList" :key="card.id" :singleCard="card"/>
</template>

<style scoped lang="scss">

</style>