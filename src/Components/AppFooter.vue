<template>
  <footer class="footer">
    <app-container>
      <div class="footer__wrapper">
        <app-menu :src="logoMuseumFooter" textColor="#555555"/>
        <app-contacts/>
      </div>
    </app-container>
  </footer>
</template>

<script>
  const logoMuseumFooter = require('../assets/img/logo/logoMuseumFooter.jpg').default;
  import AppMenu from './AppMenu.vue';
  import AppContainer from './AppContainer.vue';
  import AppContacts from './AppContacts.vue';

  export default {
    name: 'AppFooter',
    components: { AppMenu, AppContainer, AppContacts},
    computed: {
      logoMuseumFooter() { return logoMuseumFooter }
    }
  };
</script>

<style lang="scss">
  .footer {
    flex: 0 0 auto;
    min-height: 97px;
    background: #ECEAEA;
  }
  .footer__wrapper {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
</style>