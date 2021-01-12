<template>
    <div class="container">
        <slot/>
    </div>
</template>

<script>
  export default {
    name: 'AppContainer',
  };
</script>

<style lang="scss">
    .container {
      max-width: 1216px;
      margin: 0 auto;
    }
</style>