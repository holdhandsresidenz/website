<template>
  <div id="app">
    <FrontPage></FrontPage>
  </div>
</template>

<script>
import FrontPage from './pages/front-page/FrontPage'

export default {
  name: 'App',
  components: {
    FrontPage
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: 400;
  font-size: 2rem;
  letter-spacing: 2px;
  overflow: hidden;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

html, body {
  margin: 0;
}
</style>
