<template>
  <body>
  <div class="icons">

    <div class="interview-mickey">
      <VideoMickeyIcon @clicked="this.openModalVideoMickey"></VideoMickeyIcon>
    </div>

    <div class="interview-lara">
      <VideoBox @clicked="this.openModalVideoLaura"></VideoBox>
    </div>

    <div class="opencall-pdf">
      <OpenCall></OpenCall>
    </div>

    <div class="impressum">
      <ImpressumIcon @clicked="this.openModalImpressum"></ImpressumIcon>
    </div>



  </div>


    <VideoBoxModalLara
        class="VideoLauraModal"
        v-show="isModalVisibleVideoLaura"
        @close="closeModalVideoLaura"
    ></VideoBoxModalLara>

    <ImpressumModal
        class="impressumModal"
        v-show="isModalVisibleImpressum"
        @close="closeModalImpressum"
    >
    </ImpressumModal>

    <VideoMickeyModal
        class="VideoMickeyModal"
        v-show="isModalVisibleVideoMickey"
        @close="closeModalVideoMickey"
    >
    </VideoMickeyModal>

  </body>
</template>

<script>
import OpenCall from "@/pages/front-page/elements/OpenCall";
import VideoBox from "@/pages/front-page/elements/video-lara/VideoLaraIcon";
import VideoBoxModalLara from "@/pages/front-page/elements/video-lara/VideoLaraModal";
import ImpressumModal from "@/pages/front-page/elements/impressum/ImpressumModal";
import ImpressumIcon from "@/pages/front-page/elements/impressum/ImpressumIcon";
import VideoMickeyIcon from "@/pages/front-page/elements/video-mickey/VideoMickeyIcon"
import VideoMickeyModal from "@/pages/front-page/elements/video-mickey/VideoMickeyModal";


export default {
  name: "FrontPage",
  components: {

    ImpressumIcon,
    OpenCall,
    VideoBox,
   VideoBoxModalLara,
    ImpressumModal,
    VideoMickeyIcon,
    VideoMickeyModal
  },
  data: function () {
    return {
      isModalVisibleVideoLaura: false,
      isModalVisibleImpressum: false,
      isModalVisibleVideoMickey: false
    }
  },
  computed: {
    smallScreen: function () {
      return (window.innerWidth < 1000);
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
    },
    openModalVideoMickey() {
      this.isModalVisibleVideoMickey = true;
    },
    closeModalVideoMickey() {
      this.isModalVisibleVideoMickey = false;
    }
  }
}
</script>

<style scoped>
html,body {
  height: 100vh;
  width: 100vw;

}
.icons {
  position: relative;

  background: #603f3f;
  background: url("../../assets/background2.jpg") no-repeat;
  background-size: cover;

  height: 100vh;
  width: 100vw;
  overflow: hidden;

  user-select: none;
  -moz-user-select: none;
  -webkit-user-drag: none;
  -webkit-user-select: none;
  -ms-user-select: none;
}

.opencall-pdf {
  position: absolute;
  top:230px;
  left: 140px;
}

.interview-lara {
  position: absolute;
  top: 120px;
  right: 107px;
}

.impressum {
  position: absolute;
  bottom: 20px;
  left: 340px;
}

.interview-mickey {
  position: absolute;
  bottom: 40vh;
  left: 40vw;
}

@media all and (max-width: 1000px) {
  body {

  }

  .icons {
    position: relative;

    background: #603f3f;
    background-image: url("../../assets/background2.jpg") ;
    background-size: cover;

    height: 100vh;
    width: 100vw;
    overflow: hidden;

    user-select: none;
    -moz-user-select: none;
    -webkit-user-drag: none;
    -webkit-user-select: none;
    -ms-user-select: none;

  }

  .interview-lara {
    position: absolute;
    top: unset;
    left: 4vw;
    right: unset;
    bottom: 18vh;
  }
  .opencall-pdf {
    position: absolute;
    top: 10vh;
    left: 6vw;
    right: unset;
    bottom: unset;

  }
  .impressum {
    position: absolute;
    top: unset;
    left: unset;
    right: 6vw;
    bottom: 2vh;
  }

  .interview-mickey {

    position: absolute;
    top: 23vh;
    left: unset;
    right: 10vw;
    bottom: unset;
  }
}

</style>
