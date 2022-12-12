<template>
  <div id="app" >
      <login-component />
      <register-component />
      <list-component />
      <detail-component />
      <shopping-cart-component />
  </div>
</template>

<script>
import DetailComponent from './components/DetailComponent.vue'
import ListComponent from './components/ListComponent.vue'
import LoginComponent from './components/LoginComponent.vue'
import RegisterComponent from './components/RegisterComponent.vue'
import ShoppingCartComponent from './components/ShoppingCartComponent.vue'

export default {
  name: 'App',
  components: {
    LoginComponent,
    RegisterComponent,
    ListComponent,
    DetailComponent,
    ShoppingCartComponent
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  padding: 60px 30px;
  background-color:darkseagreen;
}
</style>
