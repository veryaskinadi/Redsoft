<template>
  <div class="layout__catalog">
    <layout-item v-for="catalogItem in catalog" :catalogItem="catalogItem" :key="catalogItem.id"/>
  </div>
</template>

<script>
  import LayoutItem from './LayoutItem.vue';
  
  export default {
    name: 'AppCatalog',
    components: { LayoutItem },

    data() {
      return {
        catalog: [
          {
            "id": 1,
            "title": "«Рождение Венеры»",
            "autor": "Сандро Боттичелли",
            "oldPrice": "2 000 000 $",
            "newPrice": "1 000 000 $",
            "src": 'https://i.ibb.co/gJ67cMD/painting1.jpg',
          }, 
          {
            "id": 2,
            "title": "«Тайная вечеря»",
            "autor": "Леонардо да Винчи",
            "newPrice": "3 000 000 $",
            "src": 'https://i.ibb.co/k41QYtv/painting2.jpg',
          }, 
          {
            "id": 3,
            "title": "«Сотворение Адама»",
            "autor": "Микеланджело",
            "oldPrice": "6 000 000 $",
            "newPrice": "5 000 000 $",
            "src": 'https://i.ibb.co/tZ8hhb4/painting3.jpg',
          }, 
          {
            "id": 4,
            "title": "«Урок анатомии»",
            "autor": "Рембрандт",
            "src": 'https://i.ibb.co/rv7Mcyk/painting4.jpg',
            "sold": true,
          },
        ]
      }
    }
  };
</script>

<style lang="scss">
  .layout__catalog {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
  }
</style>
