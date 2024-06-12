<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

export default{
  data(){
      return {
          
      }
  },
  components: {
    AppHeader,
    AppMain,
  }
}
</script>

<template>
  <AppHeader />
  <AppMain />
</template>

<style lang="scss">
  @use './assets/styles/general.scss';
  @use './assets/styles/partials/variables.scss' as *;
  @use './assets/styles/partials/mixins.scss' as *;
</style>
