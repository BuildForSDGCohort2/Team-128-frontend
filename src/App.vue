<template>
  <div id="app">
    <div>
      <router-view></router-view>
      <FlashMessage position="right top"></FlashMessage>
    </div>
  </div>
</template>

<script>
import * as apiService from './services/auth'
export default {
  name: 'App',
  beforeCreate: async function () {
    try {
      if (apiService.isLoggedIn()) {
        const response = await apiService.getProfile()
        this.$store.dispatch('authenticate_user', response.data.user)
      }
    } catch (error) {

    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
