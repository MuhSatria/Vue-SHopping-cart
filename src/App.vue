<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <!-- <Kasir/> -->
    <!-- <Belajar/> -->
    <MyShop/>
  </div>
</template>

<script>
import Kasir from './pages/Kasir'
import Belajar from './pages/Belanja'
import MyShop from './pages/MyShop'

export default {
  name: 'App',
  components: {
    Kasir,
    Belajar,
    MyShop
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
