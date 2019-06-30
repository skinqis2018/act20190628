<template>
  <div id="app">
    <ActBanner />
    <ActList />
    <ActPrize />
    <ActRule />
  </div>
</template>

<script>
  import './assets/less/common.less'
  import ActBanner from './views/act-banner'
  import ActList from './views/act-list'
  import ActPrize from './views/act-prize'
  import ActRule from './views/act-rule'

  export default {
    name: 'App',
    components: {
      ActBanner,
      ActList,
      ActPrize,
      ActRule
    }
  }
</script>

<style>
  #app {
    color: #fff;
    /* ,linear-gradient(to bottom,#555859,#3c3f40) */
    background: rgb(17, 14, 30) url(./img/bg-box.png) left top repeat-y;
    background-size: 100%
  }
</style>
