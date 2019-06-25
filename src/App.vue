<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <!-- <Kasir/> -->
    <MyShop/>
  </div>
</template>

<script>
import Kasir from './pages/Kasir'
import MyShop from './pages/MyShop'

export default {
  name: 'App',
  components: {
    Kasir,
    MyShop,
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
