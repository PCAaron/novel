<template>
    <div>
        <h2>示例一:按钮样式，link样式，文本样式</h2>
        <Button theme="button">按钮</Button>
        <Button theme="link">按钮</Button>
        <Button theme="text">按钮</Button>
        <h2>示例二：大，中，小</h2>
        <Button size="big">大按钮</Button>
        <Button>大按钮</Button>
        <Button size="small">小按钮</Button>
        <h2>示例三：主要，普通，危险</h2>
        <Button level="main">主要按钮</Button>
        <Button>普通按钮</Button>
        <Button level="danger">危险按钮</Button>
        <h2>示例四</h2>
        <Button disabled>按钮</Button>
        <Button>按钮</Button>
        <h2>示例五</h2>
        <Button loading>按钮</Button>
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