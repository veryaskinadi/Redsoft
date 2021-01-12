<template>
  <div class = "footer__contacts">
    <div class="footer__phone">
      <img :src=imgTel alt="" class="footer__imgTel">
      <a href="tel:+74955555555" class="footer__tel">+7 (495) 555-55-55</a>
    </div>
    <div class="footer__address">
      <img :src=imgNav alt="" class="footer__imgNav">
      <span class="footer__address">г. Москва, ул. Расплетина, 24</span>
    </div>
  </div>
</template>

<script>
  const imgTel = require('../assets/img/icon/phone.svg');
  const imgNav = require('../assets/img/icon/nav.svg');
export default {
  name: 'AppContacts.vue',
  computed: {
    imgTel() { return imgTel },
    imgNav() { return imgNav }
  }
};
</script>

<style lang="scss">
  .footer__contacts {
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 14px;
    line-height: 150%;
    color: #555555;
  }
  .footer__phone {
    padding-right: 54px;
  }
  .footer__tel {
    color: #555555;
    text-decoration: none;
  }
  .footer__imgTel {
    vertical-align: middle;
    padding-right: 3px;
  }
  .footer__imgNav {
    padding-right: 5px;
    vertical-align: middle;
  }
</style>