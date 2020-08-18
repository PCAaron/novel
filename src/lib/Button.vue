<template>
    <button class="nv-button" :class="classes" :disabled="disabled">
        <slot/>
    </button>
</template>
<script lang="ts">
import { computed } from 'vue'
export default {
    inheritAttrs: true, // 继承属性,默认true
    props: {
        theme: {
            type: String,
            default: 'button'
        },
        size: {
            type: String,
            default: 'normal'
        },
        level: {
            type: String,
            default: 'normal'
        },
        disabled: {
            type: Boolean,
            default: false
        }
    },
    setup(props) {
        const { theme, size, level } = props
        const classes = computed(() => {
            return {
                [`nv-theme-${theme}`]: theme,
                [`nv-size-${size}`]: size,
                [`nv-level-${level}`]: level
            }
        })
        return { classes }
    }
    
}
</script>
<style lang="scss">
$h:32px;
$border-color: #d9d9d9;
$color: #333;
$blue: #40a9ff;
$red: red;
$grey: grey;
$radius:4px;
.nv-button{
    box-sizing: border-box;
    height: $h;
    padding: 0 12px;
    cursor: pointer;
    display: inline-flex;
    justify-content: center;
    align-items: center;
    white-space: nowrap;
    background-color: #fff;
    color: $color;
    border:1px solid $border-color;
    border-radius: $radius;
    box-shadow: 0 1px 0 fade-out($color: #000000, $amount: 0.95);
    transition: backgroud 250ms;
    & + &{
        margin-left: 8px
    }
    &:hover,
    &：focus{
        color: $blue;
        border-radius: $blue
    }
    &:focus{
        outline: none
    }
    &::-moz-focus-inner{
        border: 0
    }
    &.nv-theme-link{
        border-color: transparent;
        box-shadow: none;
        color:$color;
        &:hover,&:focus{
            color: lighten($color: $blue, $amount: 10%)
        }
    }
    &.nv-theme-text{
        border-color: transparent;
        box-shadow: none;
        color:inherit;
        &:hover,&:focus{
            background: darken($color: #fff, $amount: 5%)
        }
    }
    &.nv-size-big{
        font-size: 24px;
        height: 48px;
        padding: 0 16px;
    }
    &.nv-size-small{
        font-size: 12px;
        height: 20px;
        padding:0 4px;
    }
    &.nv-level-main{
        background: $blue;
        color: white;
        border-color:$blue;
        &:hover,&.focus{
            background: darken($color: $blue, $amount: 10%);
            border-color: darken($color: $blue, $amount: 10%)
        }
    }
    &.nv-level-danger{
        background: $red;
        border-color: $red;
        color: white;
        &:hover,&.focus{
            background: darken($color: $red, $amount: 10%);
            border-color: darken($color: $red, $amount: 10%)
        }
    }
    &[disabled]{
        cursor: not-allowed;
        color: $grey;
        &:hover{
            border-color:$grey
        }
    }
}
</style>