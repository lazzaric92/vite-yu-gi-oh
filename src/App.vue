<script>
import AppHeader from './components/AppHeader.vue';
import AppSearch from './components/AppSearch.vue';
import AppMain from './components/AppMain.vue';

export default{
  data(){
      return {
          
      }
  },
  components: {
    AppHeader,
    AppSearch,
    AppMain,
  }
}
</script>

<template>
  <AppHeader />
  <AppSearch />
  <AppMain />
</template>

<style lang="scss">
  @use './assets/styles/general.scss';
  @use './assets/styles/partials/variables.scss' as *;
  @use './assets/styles/partials/mixins.scss' as *;
</style>
