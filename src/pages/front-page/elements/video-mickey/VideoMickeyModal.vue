<template>
  <ModalBox @close=close
            v-bind:left="vh < 1000 ? '0' : '25'"
            v-bind:right="vh < 1000 ? '0' : '25'"
            v-bind:top="vh < 1000 ? '0' : '4'"
            v-bind:bottom="vh < 1000 ? '0' : '5'"
            v-bind:border-radius="vh < 1000 ? '5' : '1.4'"
  >


  <iframe
      id="iframe-video-mickey"
  v-bind:style="{height: this.videoHeight+'px', width: this.videoWidth }"
      v-bind:height="(videoHeight + 'px')"
      v-bind:width="videoWidth+'px'"
  frameborder="0"
      src="https://www.youtube.com/embed/WwSfxtrDlJg"
  ></iframe>


  <div v-if="smallScreen" class="greenline"></div>

    <div class="biographie"
    v-bind:style="{height: bioHeight + 'px'}"
    >
      <p>
        Mickey Yang (*1988, Eindhoven, NL) lebt und arbeitet in Den Haag. Sie studierte Bildende Kunst an der
        Königlichen Akademie Den Haag und an der ArtEZ University of Arts in Arnhem, NL. Yang bezieht sich in ihren
        multimedialen Installationen oft auf Bilder eines kollektiven Gedächtnisses, um eine "Sprache der Dinge" zu
        entwickeln, die sie als inklusiver und universeller empfindet. Von 2017 bis 2018 war sie Stipendiatin bei
        Beeldenstorm/Daglicht und 2019 bei De Fabriek. Mickey Yang zeigte ihre Arbeiten in verschiedenen Einzel- und
        Gruppenausstellungen, unter anderem bei P////AKT, Amsterdam (2019), bei Art Rotterdam (2019) und in der
        Kunstvereniging Diepenheim (2017). Ihre erste Einzelausstellung in Deutschland, "Upaya" (2020) in der Kunsthalle
        Osnabrück, konnte aufgrund der Corona-Pandemie leider nicht eröffnet werden. Aktuell residiert Yang an der Jan
        van Eyck Academie in Maastricht, NL.
      </p>
      <br>
      <br>
</div>

  </ModalBox>
</template>

<script>
import ModalBox from "@/components/ModalBox";

export default {
  name: "VideoMickeyModal",
  props: {
    vh: Number,
    vw: Number
  },
  components: {
    ModalBox
  },

  methods: {
    close() {
      this.$emit('close');
      this.stopVideo();
    },
    stopVideo() {
      let player = document.getElementById('iframe-video-mickey');
      var iframeSrc = player.src;
      player.src = iframeSrc;
    },
  },
  computed: {
    videoWidth: function () {
      if (this.vw > 1000) {
        return this.vw * (0.5)
      } else {
        return this.vw
      }
    },
    videoHeight: function () {
      return this.videoWidth * 0.5625
    },
    bioHeight: function () {
      if (this.vw > 1000) {
        return ((this.vh * 0.9) - this.videoHeight) + 'px'
      }else {
        return (100 + '%')
      }
    },
    smallScreen: function () {
      return (this.vw < 1000)
    }
  }

}
</script>

<style scoped>


#iframe-video-mickey {
background: rgba(52,35,48,0);
  border: 0;
  margin: 0;
  display: block;
  padding: 0;
  border-radius: 2vw;
}

.biographie {
  position: relative;
  margin: 0;
  top:0;
  overflow: auto;
  padding-top: 0;
  padding-left: 5vw;
  padding-right: 0;
  border-radius: 2vw;

  background: #b2b2b2;
}

@media all and (max-width: 1000px) {
  .greenline {
    z-index: 5555;
    height: 22px;
    flex: 2;
    margin: 0 22px 0 22px;
    border-radius: 0;
    background: #00ff00;
  }
  .biographie {

    overflow: scroll;
    height: 100%;

    padding-left: 2vw;
    padding-right: 2vw;
    border-radius: 5vw;

  }

  #iframe-video-mickey {
    background: rgba(52,35,48,0);
    border: 0;
    margin: 0;
    display: block;
    padding: 0;
    border-radius: 5vw;
  }

}
</style>
