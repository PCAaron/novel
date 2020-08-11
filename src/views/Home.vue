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

</style>