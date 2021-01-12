<template>
    <nav class="navbar" :style="'color: ' + textColor">
        <a href="#" class="navbar__item">
            <img :src="src" alt=""  class="header__logo">
        </a>
        <a href="#" class="navbar__item">Каталог</a>
        <a href="#" class="navbar__item">Доставка</a>
        <a href="#" class="navbar__item">Оплата</a>
        <a href="#" class="navbar__item">Контакты</a>
        <a href="#" class="navbar__item">О&nbsp;галерее</a>
    </nav>
</template>

<script>
export default {
    name: 'AppMenu',

    props: {
        src: {
            type: String
        },
        textColor: {
            type: String
        }
    }
}
</script>

<style lang="scss">
    .navbar {
        width: 50%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        min-height: 97px;

    }
    .navbar__item {
        padding-right: 48px;
        text-decoration: none;
        font-size: 14px;
        line-height: 150%;
        color: inherit;
    }
</style>