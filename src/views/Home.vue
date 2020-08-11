<template>
    <div>
        <Topnav/>
        <div class="banner">
            <h1>novel-ui</h1>
            <h2>A Vue.js 3.0 UI Toolkit for Web</H2>
            <P class="actions">
                <a>Github</a>
                <a>开始</a>
            </P>
        </div>
    </div>
</template>
<script lang="ts">
import Topnav from '../components/Topnav.vue'

export default {
    components: {
        Topnav
    }
    
}
</script>
<style scoped lang="scss">
.banner{
    padding: 100px 0;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    background: lightgreen;
    > .actions{
        padding: 8px 0;
        a {
            margin:0 8px;
            background: #fff;
            display: inline-block;
            $h: 28px;
            height: $h;
            line-height: $h;
            border-radius: $h /2 ;
            padding: 0 8px;
        }
    }
}
</style>