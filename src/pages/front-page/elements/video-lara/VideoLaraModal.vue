<template>
  <transition name="modal-fade">

      <div class="container" role="dialog" aria-labelledby="modalTitle" aria-describedby="modalDescription" id="container">

        <div class="modal-sub-container" v-bind:style="{ overflow: this.overflow}">

          <section class="modal-video">
            <slot name="video">
              <div
                  style="padding:56.25% 0 0 0;
                  position:relative;">
                <iframe
                    id="iframe-video"
                    src="https://www.youtube.com/embed/lYUhY50DeR4"
                    style="position:absolute;top:0;left:0;width:100%;height:100%;"
                    frameborder="0"
                    allow="autoplay; fullscreen;"
                    allowfullscreen></iframe>
              </div>
            </slot>
          </section>
          <div class="greenline" v-if="smallScreen"></div>
          <section class="modal-bio">
            <slot name="text">
              <div class="text">
               {{text}}
              </div>
            </slot>
          </section>
  <div class="greenline" v-if="smallScreen"></div>
          <section class="modal-introtext" v-if="smallScreen">
            <slot name="bio">
              <div class="bio">
               {{bio}}
              </div>
            </slot>
          </section>
        </div>

        <section class="modal-introtext" v-if="!smallScreen">
          <slot name="bio">
            <div class="bio">
              {{bio}}
            </div>
          </slot>
        </section>

        <button
            type="button"
            class="btn-close"
            @click="close"
            aria-label="Close modal"
        >
          Close
        </button>

      </div>

  </transition>
</template>

<script>
export default {
  name: "VideoLaraModal",
  data: function () {
    return {
      videoLink: "https://player.vimeo.com/video/510192281?title=0&byline=0&portrait=0",
      smallScreen: false,
      bio: "Zur Einleitung unseres Projektes möchten wir drei Positionen vorstellen, die innerhalb des künstlerischen Feldes arbeiten, das uns interessiert. In Form von Video-Interviews, die die Künstler:innen inhaltlich selbst gestalten durften, geben sie uns einen Einblick in ihre künstlerische Praxis und Gedanken, die sie in Hinblick auf das digitale Ausstellen oder die Begehung virtueller Räume haben. Ihre Herangehensweisen und Erfahrungen in diesem Bereich fallen ganz unterschiedlich aus. Im Gespräch war Hold Hands mit den Künstler:innen Paula Ábalos, Lara Dâmaso und Mickey Yang. Jede Woche werden wir auf unserer Website ein neues Interview veröffentlichen, um uns den Fragen der Residenz — zeitlich sowie inhaltlich — immer mehr zu nähern.",
      text: "Lara Dâmaso (geb. 1996) arbeitet und lebt in Zürich. Nach einer mehrjährigen intensiven Ausbildung in Ballett und zeitgenössischem Tanz, studierte sie an der Hochschule für Grafik und Buchkunst in Leipzig im Fachbereich Medienkunst und an der Zürcher Hochschule der Künste, ZHDK, wo sie ihren Bachelor of Fine Arts erwarb. Ihre künstlerische Praxis variiert zwischen Performances, Videos, Auftritten als Performerin für verschiedene Künstler:innen und DJ-Sets. Lara’s Arbeit balanciert zwischen fokussierter Kontrolle und sinnlichem Chaos. Sie strukturiert, um zu destrukturieren und eröffnet so intime Räume, in denen ein Dialog stattfinden kann. Ihre Arbeiten wurden in verschiedenen Institutionen und Off-Spaces gezeigt, wie dem Istituto Svizzero, Centre d’Art Contemporain Genève, Kunsthalle Zürich, Cabaret Voltaire, Plymouth Rock, Kunsthalle Bern, Centre Pasqu’Art. Sie wurde für den Kiefer-Hablitzel Göhner Kunstpreis 2020 nominiert und ist nominiert für die Plattform21. Als Performerin arbeitete sie mit und für Isabel Lewis, Nile Koetting, Nikima Jagudajev, Dora Garcia, Cally Spooner/Offshore, Debora Delmar corp. und Alicia Frankovich."
    }
},
  props: {
    vh: String,
    vw: String,
  },
  computed: {
    overflow: function () {
      return this.smallScreen ? "auto" : "null"
    },
  },
  methods: {
    close() {
      this.$emit('close');
      this.stopVideo();
    },
    stopVideo() {
      let player = document.getElementById('iframe-video');
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
* {
  border-radius: 22px;
  z-index: 44;
}
.bio, .text {
  padding: 10px;
  font-size: 12pt;
  color: black;
  flex: 1;
  overflow: auto;
  min-height: 0;
}

.bio {
  padding-top: 40px;
}
.text{
  padding-top: 15px;
}

.container {
  position: absolute;
  top: 4vw;
  bottom: 5vw;
  left: 5vw;
  right: 5vw;
  width: 89vw;
  height: 89vh;
  background: rgba(0,0,0,0);
  border-radius: 22px ;
  display: flex;
  flex-direction: row;
}

.modal-sub-container {
  display: flex;
  flex: 3;
  flex-direction: column;
  height: auto;
}

.modal-bio {

  background: #b2b2b2;
  overflow: auto;
}
.modal-video {
  flex: 1;
  background: gray;
}
.modal-introtext {
  flex: 1;
  display: flex;
  background: #b2b2b2;
}

.background {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: rgba(0, 0, 0, 1);
  display: flex;
  justify-content: center;
  align-items: center;
}

.btn-close {
  font-family: Narr, sans-serif;
  font-size: 20pt;
  cursor: pointer;
  height: 40px;
  width: 80px;
  position: absolute;
  right: 0px;
  color: #b2b2b2;
  background: #0015ff;
  border: 0;
}

@media all and (max-width: 1000px) {
  .greenline {
    z-index: 5555;
    height: 22px;
    margin: 0  22px 0 22px;
    border-radius: 0;
    background: #00ff00;
  }
  .modal-sub-container::-webkit-scrollbar {
    width: 0px;
  }
  .modal-sub-container {
    background: rgba(0,0,0,0);
    display: block;
    border-radius: 0;
  }
  .container {
    top:0;
    width: 100vw;
    height: 100vh;
    background: rgba(0,0,0,0);
    border-radius: 22px ;
  }

  .modal-introtext {
    background: #b2b2b2;
  }
  .modal-bio {
    background: #b2b2b2;
  }
  .bio, .text {
    padding: 10px;
    padding-top: 15px;
    font-size: 12pt;
    color: black;
  }
}
</style>
