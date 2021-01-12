<template>
  <div class="header__search">
    <input class="header__input" type="text" placeholder="Поиск по названию картины">
    <app-button buttonText="Найти" :width="122" background="var(--normal-button)">
     <div>
       <span>Найти</span>
     </div>
    </app-button>
  </div>
</template>

<script>
import AppButton from './AppButton.vue';
export default {
  name: 'AppSearch.vue',
  components: { AppButton },
};
</script>

<style lang="scss">
  .header__search {
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .header__input {
    background: #F6F3F3;  
    width:294px;
    height: 48px;
    font-size: 14px;
    line-height: 150%;
    border: 1px solid var(--border-color);
    border-right: none;
    color: #9F9F9F;
    padding: 0;
    padding-left: 16px;
    box-sizing: border-box;
    outline: none;
    &:focus {
      border: 1px solid #B5B5B5;
      border-right: none;
    }
  }
</style>