<template>
  <div class="wrapper" id="app">
    <app-header/>
    <app-layout/>
    <app-footer/>
  </div>
</template>

<script>
import AppHeader from './Components/AppHeader.vue';
import AppLayout from './Components/AppLayout.vue';
import AppFooter from './Components/AppFooter.vue';

export default {
  name: 'App.vue',
  components: { AppHeader, AppLayout, AppFooter},  
  css: {
    extract: true
  },

  mounted() {
    if (!localStorage.cart) {
      localStorage.cart = JSON.stringify([])
    }
  },
};
</script>
  
<style lang="scss">
  .wrapper {
    display: flex;
    flex-direction: column;
    height: 100%;
  }
</style>
