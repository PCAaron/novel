<template>
    <button class="nv-button" :class="`nv-theme-${theme}`">
        <slot/>
    </button>
</template>
<script lang="ts">
export default {
    inheritAttrs: true, // 继承属性,默认true
    props: {
        theme: {
            type: String,
            default: 'button'
        }
    }
    
}
</script>
<style lang="scss">
$h:32px;
$border-color: #d9d9d9;
$color: #333;
$blue: #40a9ff;
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
}
</style>