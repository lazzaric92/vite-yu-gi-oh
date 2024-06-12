<script>
import { store } from "../store.js";

export default{
    data(){
        return {
            store
        }
    },
    props: {
        singleCard: {
            type: Object,
            required: true,
        }
    }
}
</script>

<template>
    <article>
        <div class="card-image">
            <img :src="singleCard.card_images[0].image_url" :alt="singleCard.name">
        </div>
        <div class="card-info">
            <h3> {{ singleCard.name }} </h3>
            <p> {{ singleCard.archetype }} </p>
        </div>
    </article>
</template>

<style scoped lang="scss">
    @use '../assets/styles/partials/variables' as *;
    @use '../assets/styles/partials/mixins' as *;

    article {
        width: calc((100% / 5) - 1.5rem);
        margin-bottom: 1rem;
        background-color: $bg-orange;

        .card-image{
            width: 100%;

            img {
                width: 100%;
            }
        }

        .card-info {
            text-align: center;
            padding: .2rem;

            h3 {
                color: white;
                text-transform: uppercase;
                margin: 1rem 0;
            }

            p {
                font-size: 1.2rem;
            }
        }
    }
</style>