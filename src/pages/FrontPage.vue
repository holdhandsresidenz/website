<template>
  <body>
  <div class="opencallPosition">
    <OpenCall></OpenCall>
  </div>
  <div class="video1Position">
    <VideoBox></VideoBox>
  </div>
  </body>
</template>

<script>
import OpenCall from "@/components/OpenCall";
import VideoBox from "@/components/VideoBox";

export default {
  name: "FrontPage",
  components: {
    OpenCall,
    VideoBox
  }
}
</script>

<style scoped>
html, body {
  background: #603f3f;
  background: url("../assets/background.jpg") no-repeat;
  background-size: cover;
  height: 100vh;
  width: 100vw;
  padding: 0;
}

.opencallPosition {
  float: left;
  padding-top: 31vh;
  padding-left: 15vw;
}

.video1Position {
  float: right;
  padding-right: 22vw;
  padding-top: 20vh;
}


@media all and (max-width: 1000px) {

}


</style>
