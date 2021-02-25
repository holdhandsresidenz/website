<template>
  <body>

  <div class="opencallPosition">
    <OpenCall></OpenCall>
  </div>

  <div class="video1Position">
    <VideoBox @clicked="this.openModal"></VideoBox>
  </div>

  <div>
    <VideoBoxModal
        v-show="isModalVisible"
        @close="closeModal"
    ></VideoBoxModal>
  </div>

  </body>
</template>

<script>
import OpenCall from "@/pages/front-page/elements/OpenCall";
import VideoBox from "@/pages/front-page/elements/VideoLara";
import VideoBoxModal from "@/pages/front-page/elements/VideoLaraModal";

export default {
  name: "FrontPage",
  components: {
    OpenCall,
    VideoBox,
    VideoBoxModal
  },
  data: function () {
    return {
      isModalVisible: false,
    }
  },
  methods: {
    openModal() {
      this.isModalVisible = true;
    },
    closeModal() {
      this.isModalVisible = false;

    }
  }
}
</script>

<style scoped>
html, body {
  background: #603f3f;
  background: url("../../assets/background.jpg") no-repeat;
  background-size: cover;
  height: 100vh;
  width: 100vw;
  padding: 0;
  overflow: hidden;
}

.opencallPosition {
  float: left;
  padding-top: 31vh;
  padding-left: 15vw;
}

.video1Position {
float: right;
  padding-right: 22vw;
padding-top: 78vh;
}


@media all and (max-width: 1000px) {
  .video1Position {
    float: right;
    padding-right: 12vw;
    padding-top: 10vh;
  }
}


</style>
