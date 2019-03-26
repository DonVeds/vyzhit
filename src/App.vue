<template>
  <div id="app">
    <SearchBlock/>
    <CalcButton/>
    <MainList/>
  </div>
</template>

<script>
import SearchBlock from './components/SearchBlock.vue'
import HelloWorld from './components/HelloWorld.vue'
import CalcButton from './components/CalcButton.vue'
import MainList from './components/MainList.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    SearchBlock,
    CalcButton,
    MainList
  }
}
</script>

<style lang='sass'>
@import '../node_modules/bulma/bulma.sass'

#app
  position: fixed
  top: 0
  left: 0
  width: 100%
  height: 100%

</style>
