<template>
    <div>
        <h2>示例</h2>
        <Button theme="button">按钮</Button>
        <Button theme="link">按钮</Button>
        <Button theme="text">按钮</Button>
    </div>
</template>
<script lang="ts">
import Button from '../lib/Button.vue'
export default {
    components: {
        Button
    },
    setup() {
        const onClick = () =>{

        }
        return {onClick}
    }
}
</script>