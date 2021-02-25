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
  line-height: 200%;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  text-align: left;
  color: #2c3e50;
}

*::-webkit-scrollbar {
  width: 11px;
}
*::-webkit-scrollbar-track {
  background: #00ff00;

}
*::-webkit-scrollbar-thumb {
  background: #000;

}
*::-webkit-scrollbar-thumb:hover {
  background: #000;

}

@font-face {
  font-family: 'Akzi';
  src: url("./assets/fonts/AkzidGroMed.woff") format("woff");
}

@font-face {
  font-family: 'Narr';
  src: url("./assets/fonts/Arial-Narrow.woff") format("woff");
}

html, body {
  margin: 0;
}
</style>
