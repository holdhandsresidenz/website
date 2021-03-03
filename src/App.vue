<template>
  <div id="app">
    <FrontPage id="front-page"></FrontPage>
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
html, body {
  margin: 0;
}
#app {
  font-family: Akzi, sans-serif;
  line-height: 200%;
  text-align: left;
  color: black;
  scroll-behavior: smooth;
  -webkit-overflow-scrolling: touch
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

</style>
