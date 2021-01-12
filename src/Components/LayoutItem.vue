<template>
    <div class="layout__catalogItem" :class="catalogItem.sold ? 'layout__catalogItem_sold' : ''">
        <img class="layout__catalogItem-Img" alt="" :src="catalogItem.src" />
        <h2 class="layout__catalogItem-title">{{ catalogItem.title }}<br/>{{ catalogItem.autor }}</h2>
        <div v-if="!catalogItem.sold" class="layout__catalogItem-footer">
            <div class="layout__prices">
                <div class="layout__old-price">{{ catalogItem.oldPrice }}</div>
                <div class="layout__new-price">{{ catalogItem.newPrice }}</div>
            </div>
            <app-button @click.native="addToCart()" :width="118" :background="stateInfo.buttonBackground">
                <div class="layout__buttonContent">
                    <img v-if="state=='addedToCart'" :src="checkButton" alt="check" class="layout__checkButton">
                    <span>{{stateInfo.buttonText}}</span>
                </div>
            </app-button>
        </div>
        <div v-else class="layout__catalogItem-footer">
            <span class="layout__catalogItem-soldText">Продана на аукционе</span>
        </div>
    </div>
</template>

<script>
    const  checkButton = require('../assets/img/icon/check.svg').default;
    import AppButton from './AppButton.vue'
    export default {
        components: { AppButton },
        name: 'LayoutItem',

        props: {
            catalogItem: {
                type: Object
            },
        },

        data() {
            return {
                state: "default"
            }
        },

        mounted() {
            if (localStorage.cart) {
                const cart = JSON.parse(localStorage.cart)
                if (cart.includes(this.catalogItem.id)) {
                    this.state = "addedToCart"
                }
            }
            
        },

        computed: {
            stateInfo() {
                switch (this.state) {
                    case "default":
                        return {buttonText: "Купить", buttonBackground: "var(--normal-button)"}
                        break
                    case "load":
                        return {buttonText: "↺", buttonBackground: "var(--normal-button)"} 
                        break
                    case "addedToCart":
                        return {buttonText: "В корзине", buttonBackground: "var(--cart-button)"} 
                        break
                }
            },
            checkButton() { return checkButton }
        },

        methods: {
            async addToCart() {
                if (this.state === "default") {
                    this.state = "load"
                    const response = await fetch("https://jsonplaceholder.typicode.com/posts/" + this.catalogItem.id);
                    if (response.ok) {
                        const cart = JSON.parse(localStorage.cart)
                        cart.push(this.catalogItem.id)
                        localStorage.cart = JSON.stringify(cart)
                        this.state = "addedToCart"
                    }
                } else if (this.state === "addedToCart") {
                    this.state = "load"
                    const cart = JSON.parse(localStorage.cart)
                    cart.splice(cart.indexOf(this.catalogItem.id), 1)
                    localStorage.cart = JSON.stringify(cart)
                    this.state = "default"
                }
            }
        }
    }
</script>

<style lang="scss">
    .layout__catalogItem {
        border: 1px solid var(--border-color);
        width: 280px;
        height: 328px;
        overflow: hidden;
        margin-top: 18px;
    }
    .layout__catalogItem-footer {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin: 24px;
    }
    .layout__catalogItem-title {
        margin-left: 24px;
        margin-top: 16px;
        font-size: 18px;
        line-height: 150%;
    }
    .layout__old-price {
        text-decoration-line: line-through;
        color: #A0A0A0;
        font-weight: 300;
        font-size: 14px;
    }
    .layout__new-price {
        font-weight: bold;
        font-size: 16px;
        line-height: 150%;
    }
    .layout__catalogItem-soldText {
        font-weight: bold;
        font-size: 16px;
        line-height: 55px;
        color: var(--text-color);
    }
    .layout__catalogItem_sold {
        opacity: 0.5;
    }
    .layout__buttonContent{
        display: flex;
        justify-content: center;
    }
    .layout__checkButton {
        padding-right: 5px;
    }
</style>