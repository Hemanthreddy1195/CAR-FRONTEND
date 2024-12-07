<template>
  <IndexPage />
  <FooterMainPage/>
</template>

<script>
import IndexPage from './components/IndexPage.vue'
import FooterMainPage from './components/FooterMainPage.vue'

export default {
  name: 'App',
  components: {
    IndexPage,
    FooterMainPage
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
}
</style>

