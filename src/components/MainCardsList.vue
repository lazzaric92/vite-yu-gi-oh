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
            <p v-if="this.store.cardsList.length > 0">Found {{ store.cardsList.length }} cards</p>
            <p v-else>Select an archetype</p>
        </div>
        <div class="card-wrapper">
            <template v-if="this.store.cardsList.length > 0">
                <MainSingleCard v-for="card in store.cardsList" :key="card.id" :singleCard="card"/>
            </template>
        </div>
    </section>
</template>

<style scoped lang="scss">
    @use '../assets/styles/partials/variables' as *;
    @use '../assets/styles/partials/mixins' as *;

    section {
        background-color: white;
        padding: 3rem 3rem 2rem;
        margin: 1rem 0 2rem;

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
            justify-content: space-around;
        }
    }
</style>