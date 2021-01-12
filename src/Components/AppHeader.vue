<template>
  <header class="header">
    <app-container>
      <div class="header__wrapper">
        <app-menu :src="logoMuseum" textColor="var(--text-color)"/>
        <app-search/>
      </div>
     
    </app-container>
  </header>
  
</template>

<script>
  const logoMuseum = require('../assets/img/logo/logoMuseum.jpg').default;
  import AppMenu from './AppMenu.vue';
  import AppSearch from './AppSearch.vue';
  import AppContainer from './AppContainer.vue';
  
  export default {
    name: 'AppHeader',
    components: { AppContainer, AppMenu, AppSearch },
    computed: {
      logoMuseum() { return logoMuseum }
    }
  };
</script>

<style lang="scss">
  .header {
    flex: 0 0 auto;
    background: var(--background);  
    min-height: 95px;
    border-top: 1px solid var(--border-color);
    border-bottom: 1px solid var(--border-color);
  }
  .header__wrapper {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
</style>
