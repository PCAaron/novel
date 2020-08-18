<template>
    <div>
        <button class="nv-switch" :class="{checked: value}" @click="toggleSwitch"><span></span></button>
    </div>
</template>
<script lang="ts">
import { ref } from 'vue'
export default {
    props: {
        value: {
            type: Boolean,
            default: false
        }
    },
    setup(props, context) {
        const toggleSwitch = () =>{
            context.emit('update:value', !props.value)
        }
        return {
            toggleSwitch
        }
    }
}
</script>
<style lang="scss">
$h: 22px;
$h2: $h - 4px;
.nv-switch{
    height: $h;
    width: $h*2;
    border:none;
    background: grey;
    border-radius: $h/2;
    position: relative;
    span{
        position: absolute;
        top:2px;
        left:2px;
        height:$h2;
        width: $h2;
        background: white;
        border-radius: $h2/2;
        transition: left 250ms ease;
    }
    &.checked{
        background: blue;
        > span{
            left: calc(100% - #{$h2} - 2px);
        }
    }
}
.nv-switch:focus{
    outline: none
}
</style>