<template>
  <div id="app">
    <FrontPage></FrontPage>
  </div>
</template>

<script>
import FrontPage from './pages/FrontPage'

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
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
html, body {
  background: #533D4A;
  margin: 0;
  font-family:'ArialNarrow', sans-serif;
  src: url('assets/fonts/ArialNarrow.ttf');
  font-style: normal;
  font-weight:400;
  font-size: 2rem;
  font-stretch: 1% 500%; /* Required by Chrome */
  overflow: hidden;
}
</style>
