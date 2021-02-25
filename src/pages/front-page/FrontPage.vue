<template>
  <body>

  <div class="opencallPosition">
    <OpenCall></OpenCall>
  </div>

  <div class="video1Position">
    <VideoBox @clicked="this.openModalVideoLaura"></VideoBox>
  </div>

  <div class="impressumPosition">
    <Impressum @clicked="this.openModalImpressum"></Impressum>
  </div>


  <div>
    <VideoBoxModal
        class="VideoLaura"
        v-show="isModalVisibleVideoLaura"
        @close="closeModalVideoLaura"
    ></VideoBoxModal>
  </div>

  <div>
    <ImpressumModal
        class="impressum"
        v-show="isModalVisibleImpressum"
        @close="closeModalImpressum"
    >
    </ImpressumModal>
  </div>
  </body>
</template>

<script>
import OpenCall from "@/pages/front-page/elements/OpenCall";
import VideoBox from "@/pages/front-page/elements/VideoLara";
import VideoBoxModal from "@/pages/front-page/elements/VideoLaraModal";
import ImpressumModal from "@/pages/front-page/elements/ImpressumModal";
import Impressum from "@/pages/front-page/elements/Impressum";

export default {
  name: "FrontPage",
  components: {
    Impressum,
    OpenCall,
    VideoBox,
    VideoBoxModal,
    ImpressumModal
  },
  data: function () {
    return {
      isModalVisibleVideoLaura: false,
      isModalVisibleImpressum: false,
    }
  },
  methods: {
    openModalVideoLaura() {
      this.isModalVisibleVideoLaura = true;
    },
    closeModalVideoLaura() {
      this.isModalVisibleVideoLaura = false;
    },
    openModalImpressum() {
      this.isModalVisibleImpressum = true;
    },
    closeModalImpressum() {
      this.isModalVisibleImpressum = false;
    }
  }
}
</script>

<style scoped>
html, body {
  background: #603f3f;
  background: url("../../assets/background2.jpg") no-repeat;
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
  position: absolute;
  top: 12%;
  right: 50px;
}

.impressumPosition {
position: absolute;
bottom: 2%;
  left: 4%;
}


@media all and (max-width: 1000px) {
  .video1Position {
    position: absolute;
    top: unset;
    bottom: 0px;
    right: 42px;
  }
  .opencallPosition {
    position: absolute;
    padding: 0;
    top: 18%;
    left: 10%;
  }
  .impressumPosition {
    position: absolute;
    bottom: 12px;
    left: 4%;
  }
}


</style>
