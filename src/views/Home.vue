<template>
    <div>
        <div class="topnav">
            <div class="logo">LOGO</div>
            <ul class="menu">
                <li>菜单1</li>
                <li>菜单2</li>
            </ul>
        </div>
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
<style scoped lang="scss">
.topnav{
    background: pink;
    display: flex;
    padding: 16px;
    > .logo{
        max-width: 6em;
        margin-right: auto;
    }
    > .menu{
        display: flex;
        white-space: nowrap;
        flex-wrap: nowrap;
        > li{
            margin: 0 1em;
        }
    }
}
</style>