<script>
import HeaderApp from './components/HeaderApp.vue';
import MainApp from './components/MainApp.vue';
import FooterApp from './components/FooterApp.vue';
import AppLoader from './components/AppLoader.vue';
  export default {
    name: 'App',
    components: {
      HeaderApp,
      MainApp,
      FooterApp,
      AppLoader
    }, 
    data() {
    return {
      showLoader: true,
    };
  },
  mounted() {
    this.loadingComplete();
  },
  methods: {
    loadingComplete(){
      window.addEventListener('load', () => {
      console.log('FATTO AMMO');
      setTimeout(()=>{
        this.showLoader = false;
      }, 1000);
    });
    }
  }
  }
</script>

<template>
    <div class="app" :class="showLoader ? 'hidden' : ''">
      <HeaderApp />
      <MainApp />
      <FooterApp />
    </div>
    <div class="loader" :class="showLoader ? '' : 'd-none'">
      <AppLoader />
    </div>
</template>

<style lang="scss">
  @import url('./styles/general.scss');
</style>
