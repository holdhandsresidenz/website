<template>
<body>
<OpenCall></OpenCall>
</body>
</template>

<script>
import OpenCall from "@/components/OpenCall";

export default {
  name: "FrontPage",
  components: {
    OpenCall
  }
}
</script>

<style scoped>
html,body {
  background: #603f3f;
  background: url("../assets/background.jpg") no-repeat;
  background-size: cover;
  height: 100vh;
  width: 100vw;
  padding: 0;
}
/*
OpenCall {
  position: relative;
  float: left;
  width: 35vw;
  height: 35vw;
  padding-top: 11vh;
  padding-left: 2vw;

}

@media all and (max-width: 1000px) {
  OpenCall {
    position: relative;
    width: 100vw;
    height: 50vw;
    margin-top: 30vh;
    padding-left: 22vw;
  }
}

 */

</style>
