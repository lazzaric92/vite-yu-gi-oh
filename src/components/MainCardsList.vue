<script>
import MainSingleCard from './MainSingleCard.vue';

export default{
    data(){
        return {
            message: 'Here\'s the cards'
        }
    },
    components: {
        MainSingleCard
    }
}
</script>

<template>
    <h1> {{ message }} </h1>
    <MainSingleCard />
</template>

<style scoped lang="scss">

</style>