<template>
    <div class="layout">
        <Topnav class="nav"/>
        <div class="container">
            <aside v-if="asideVisible">
                <h2>组件列表</h2>
                <ol>
                    <li>
                        <router-link to='/doc/switch'>Switch 组件</router-link>
                    </li>
                    <li>
                        <router-link to='/doc/button'>Button 组件</router-link>
                    </li>
                    <li>
                        <router-link to='/doc/dialog'>Dialog 组件</router-link>
                    </li>
                    <li>
                        <router-link to='/doc/tabs'>Tabs 组件</router-link>
                    </li>
                </ol>
            </aside>
            <main>
                <router-view/>
            </main>
        </div>
    </div>
</template>
<script lang="ts">
import Topnav from '../components/Topnav.vue'
import { inject, Ref } from 'vue'
export default {
    components: {
        Topnav
    },
    setup() {
        const asideVisible = inject<Ref<boolean>>('asideShow')
        return {asideVisible}
    }
}
</script>
<style scoped lang="scss">
.layout{
    display: flex;
    flex-direction: column;
    height: 100vh;
    > .nav{
        flex-shrink: 0;
    }
    > .container{
        flex-grow: 1;
        padding-top: 60px;
        padding-left: 156px;
        @media (max-width: 768px) {
            padding-left: 0
        }
    }
}
.container{
    display: flex;
    > aside{
        flex-shrink: 0;
    }
    > main{
        flex-grow: 1;
        padding: 16px;
        background: transparent;
    }
}
aside{
    background: lightblue;
    width: 150px;
    padding: 16px;
    position: fixed;
    top: 0;
    left: 0;
    padding-top: 70px;
    height: 100%;
    > h2{
        margin-bottom: 4px;
    }
    > ol {
        >li {
            padding: 4px 0
        }
    }
}
main{
    overflow: auto;
}
</style>