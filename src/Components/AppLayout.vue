<template>
  <section class="layout">
      <app-container>
        <h1 class="layout__title">Картины эпохи Возрождения</h1>
        <app-catalog/>
      </app-container>
  </section>
</template>

<script>
  import AppContainer from './AppContainer.vue';
  import AppCatalog from './AppCatalog.vue';
  
  export default {
    name: 'AppLayout',
    components: { AppContainer, AppCatalog },
  };
</script>

<style lang="scss">
  .layout {
    flex: 1 0 auto;
    background: var(--background); 
    padding-bottom: 30px;
  }
  .layout__title {
    color: var(--text-color);
    font-weight: bold;
    font-size: 24px;
    line-height: 150%;
    margin-top: 0;
    padding-top: 43px;
  }
</style>
