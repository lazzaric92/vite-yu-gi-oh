<script>
import MainCardsList from './MainCardsList.vue';

export default{
    data(){
        return {
            message: 'Main'
        }
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