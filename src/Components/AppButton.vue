<template>
    <button class="button" :style="`width:${width}px; background:${background}`"><slot/></button>
</template>

<script>
export default {
    name: 'AppButton.vue',

    props: {
        width: {
            type: Number,
            required: true
        },
        background: {
            type: String
        }
  },
};
</script>

<style lang="scss">
    .button {
        font-family: 'Merriweather', serif;
        height: 48px;
        border: none;
        font-weight: bold;
        font-size: 14px;
        line-height: 150%;
        color: #FFFFFF;
        &:focus {
            outline: none;
        }
    }
</style>