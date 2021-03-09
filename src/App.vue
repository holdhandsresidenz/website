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
  line-height: 2.4vw;
  text-align: left;
  color: black;
  font-size: 1.23vw;
  scroll-behavior: smooth;
  -webkit-overflow-scrolling: touch
}


p, address{
  transform:scaleX(0.85) translateX(-9.92vw);
  width: 117.6%;
}
*::-webkit-scrollbar {
  width: 11px;
  transform: translate(-40px);
}
*::-webkit-scrollbar-track {
  background: #00ff00;
  border-radius: 2vw ;
}
*::-webkit-scrollbar-thumb {
  background: #000;
  border-radius: 2vw ;
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
@media all and (max-width: 1000px) {
  #app{
    line-height: 200%;
    font-size: 13pt;
  }
  *::-webkit-scrollbar {
    width: 0px;
    transform: translate(-40px);
  }
  }
</style>
