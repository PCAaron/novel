<template>
    <div>
        <Switch v-model:value="_val"/>
        <div>Switch组件值：{{_val}}</div>
    </div>
</template>
<script lang="ts">
import Switch from '../lib/Switch.vue'
import { ref } from 'vue'
export default {
    components: {
        Switch
    },
    setup() {
        const _val = ref(true)
        return {_val}
    }
}
</script>
