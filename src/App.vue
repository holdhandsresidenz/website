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
  font-family: Akzi, sans-serif;
  overflow: hidden;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  text-align: justify;
  color: #2c3e50;

}
@font-face {
  font-family: 'Akzi';
  src: url("./assets/fonts/AkzidGroMed.woff") format("woff");
  src: url("./assets/fonts/Arial-Narrow.woff") format('woff');
}

html, body {
  margin: 0;
}
</style>
