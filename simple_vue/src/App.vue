<template>
  <div id="app">
    <img src="./assets/logo.jpg">
    <drinklist></drinklist>
  </div>
</template>

<script>
import drinklist from './components/DrinkList'

export default {
  name: 'app',
  data () {
    return {
      msg: ''
    }
  },
  components:{
    drinklist,
  }
}
</script>

<style lang="scss">
#app {

  text-align: center;
  margin-top: 60px;
}

img {
  height: 8rem;
  text-align: center;

  margin-top: 30px;
  margin-bottom: 30px
}
</style>
