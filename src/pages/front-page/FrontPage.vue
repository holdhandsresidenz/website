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

    <div class="datenschutz">
      <DatenschutzIcon  @clicked="this.openModalDatenschutz"></DatenschutzIcon>
    </div>

  </div>


    <VideoBoxModalLara
        class="VideoLauraModal"
        v-if="isModalVisibleVideoLaura"
        @close="closeModalVideoLaura"
        v-bind:vh="vh"
        v-bind:vw="vw"
    ></VideoBoxModalLara>

    <ImpressumModal
        class="impressumModal"
        v-if="isModalVisibleImpressum"
        @close="closeModalImpressum"
        v-bind:vh="vh"
        v-bind:vw="vw"
    >
    </ImpressumModal>

    <DatenschutzModal
        class="datenschutzModal"
        v-if="isModalVisibleDatenschutz"
        @close="closeModalDatenschutz"
        v-bind:vh="vh"
        v-bind:vw="vw"
    >
    </DatenschutzModal>

    <VideoMickeyModal
        class="VideoMickeyModal"
        v-if="isModalVisibleVideoMickey"
        @close="closeModalVideoMickey"
        v-bind:vh="vh"
        v-bind:vw="vw"
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
import DatenschutzModal from "@/pages/front-page/elements/datenschutz/DatenschutzModal";
import DatenschutzIcon from "@/pages/front-page/elements/datenschutz/DatenschutzIcon";


export default {
  name: "FrontPage",
  components: {
    DatenschutzIcon,
    DatenschutzModal,

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
      isModalVisibleVideoMickey: false,
      isModalVisibleDatenschutz: false,
      vw: 1920,
      vh: 1080
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
    },
    openModalDatenschutz() {
      this.isModalVisibleDatenschutz = true;
    },
    closeModalDatenschutz() {
      this.isModalVisibleDatenschutz = false;
    },
    updateSize() {
      console.log("updateds")
      this.vh = window.innerHeight
      this.vw = window.innerWidth
    }
  },
  created() {
    this.updateSize()
    window.addEventListener('resize', this.updateSize)
  },
  destroyed() {
    window.removeEventListener("resize", this.updateSize)
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
  background: url("../../assets/background.jpg") no-repeat;
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
  left: 37vw;
}

.datenschutz{
  position: absolute;
  bottom: 40vh;
  right: 17vw;
}

@media all and (max-width: 1000px) {
  body {

  }

  .icons {
    position: relative;

    background: #603f3f;
    background-image: url("../../assets/background.jpg") ;
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
    bottom: 5vh;
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
    bottom: 0vh;
  }

  .datenschutz{
    position: absolute;
    bottom: 40vh;
    left: 17vw;
  }

  .interview-mickey {
    position: absolute;
    top: 24vh;
    left: unset;
    right: 0vw;
    bottom: unset;
  }
}

</style>
