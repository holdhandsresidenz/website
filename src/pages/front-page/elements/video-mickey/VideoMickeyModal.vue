<template>
  <ModalBox  @close=close>
    <div class="container">

        <section class="video">
          <div class="framing">
            <iframe
                id="iframe-video-mickey"
                src="https://www.youtube.com/embed/WwSfxtrDlJg"
                frameborder="0"
                allow="autoplay; fullscreen;"
                allowfullscreen></iframe>
            </div>
        </section>
      <div class="greenline" v-if="smallScreen"></div>
        <section class="biographie">
          Mickey Yang (*1988, Eindhoven, NL) lebt und arbeitet in Den Haag. Sie studierte Bildende Kunst an der Königlichen Akademie Den Haag und an der ArtEZ University of Arts in Arnhem, NL. Yang bezieht sich in ihren multimedialen Installationen oft auf Bilder eines kollektiven Gedächtnisses, um eine "Sprache der Dinge" zu entwickeln, die sie als inklusiver und universeller empfindet. Von 2017 bis 2018 war sie Stipendiatin bei Beeldenstorm/Daglicht und 2019 bei De Fabriek. Mickey Yang zeigte ihre Arbeiten in verschiedenen Einzel- und Gruppenausstellungen, unter anderem bei P////AKT, Amsterdam (2019), bei Art Rotterdam (2019) und in der Kunstvereniging Diepenheim (2017). Ihre erste Einzelausstellung in Deutschland, "Upaya" (2020) in der Kunsthalle Osnabrück, konnte aufgrund der Corona-Pandemie leider nicht eröffnet werden. Aktuell residiert Yang an der Jan van Eyck Academie in Maastricht, NL.
        </section>

    </div>

  </ModalBox>
</template>

<script>
import ModalBox from "@/components/ModalBox";
export default {
name: "VideoMickeyModal",
  components: {
  ModalBox
  },
   data: function () {
  return {
    smallScreen: false,
    }
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
    }
  },
  mounted() {
    if (screen.width < 1000) {
      this.smallScreen = true;
    }
  }
}
</script>

<style scoped>
*{
  border-radius: 22px;
}
.container {
  display: flex;
  flex-direction: column;
}

.video {
flex: 2;
}
.framing {
  width:100%;height:100%;
}
#iframe-video-mickey {
  position:relative;width:100%;height:100%;
}
  .biographie {
flex: 1;
    padding: 10px 10px 0px 10px;
    font-size: 12pt;
    color: black;
    overflow: auto;
    background: #b2b2b2;
  }
@media all and (max-width: 1000px) {
    .greenline {
      z-index: 5555;
      height: 22px;
      flex: 2;
      margin: 0  22px 0 22px;
      border-radius: 0;
      background: #00ff00;
    }
  .container {
    overflow: auto;
    border-radius: 0;
    display: block;
  }
  .video {
    flex: unset;
    width: 100%;

  }
  .biographie{
    flex: unset;
    overflow: unset;
  }
  .framing {
    width: unset;
    height: unset;
    padding:56.25% 0 0 0;
    position:relative;
  }
  #iframe-video-mickey {
    position:absolute;top:0;left:0;width:100%;height:100%;
  }
    .biographie::-webkit-scrollbar {
      width: 0px;
    }
}
</style>
