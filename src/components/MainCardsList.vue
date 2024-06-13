<script>
import MainSingleCard from './MainSingleCard.vue';
import { store } from "../store.js";

export default{
    data(){
        return {
            store,
        }
    },
    components: {
        MainSingleCard
    }
}
</script>

<template>
    <section>
        <div>
            <p>Found {{ store.cardsList.length }} cards</p>
        </div>
        <div class="card-wrapper">
            <MainSingleCard v-for="card in store.cardsList" :key="card.id" :singleCard="card"/>
        </div>
    </section>
</template>

<style scoped lang="scss">
    @use '../assets/styles/partials/variables' as *;
    @use '../assets/styles/partials/mixins' as *;

    section {
        background-color: white;
        padding: 3rem;

        div:first-child {
            background-color: $bg-darkgrey;
            color: white;
            padding: 1rem;
            font-weight: bold;
            margin-bottom: 1rem;
        }

        .card-wrapper {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
        }
    }
</style>