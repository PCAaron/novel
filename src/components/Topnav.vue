<template>
  <div class="topnav">
    <ul class="toggleAside" @click="toggleAside">
      <li v-for="i in 3" :key="i"></li>
    </ul>
    <div class="logo">LOGO</div>
    <ul class="menu">
      <li>菜单1</li>
      <li>菜单2</li>
    </ul>
  </div>
</template>
<script lang="ts">
import { inject, Ref } from 'vue'
export default {
  setup() {
    const asideVisible = inject<Ref<boolean>>('asideShow')
    console.log(asideVisible.value)
    const toggleAside = () =>{
      asideVisible.value = !asideVisible.value
    }
    return { toggleAside }
  }
}
</script>
<style lang="scss" scoped>
.topnav{
    background: pink;
    display: flex;
    padding: 16px;
    position: relative;
    z-index: 10;
    justify-content: center;
    align-items: center;
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
    > .toggleAside{
      display: inline-block;
      width: 40px;
      background-color: red;
      display: none;
      > li{
        width: 100%;
        height: 1px;
        background: #fff;
        margin-top: 10px;
        &:last-child{
          background: transparent
        }
      }
    }
  @media (max-width: 768px) {
    > .menu{
      display: none
    }
    > .logo{
      margin: 0 auto;
    }
    > .toggleAside{
      display: inline-block
    }
  }
}
</style>