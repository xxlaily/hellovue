<template>
  <img alt="Vue logo" src="./assets/logo.png">
<!--  <MyVue></MyVue>
  <Nav></Nav>-->
  <News></News>
</template>

<script>
/*import MyVue from "./components/MyVue";
import Nav from "./components/Nav";*/
import News from "./components/News";
export default {
  name: 'App',
  components: {
    /*MyVue,
    Nav*/
    News
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
