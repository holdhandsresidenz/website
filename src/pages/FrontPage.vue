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



@media all and (max-width: 1000px) {

}


</style>
