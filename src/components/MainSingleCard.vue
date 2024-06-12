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
    <p> {{ singleCard.name }} </p>
</template>

<style scoped lang="scss">

</style>