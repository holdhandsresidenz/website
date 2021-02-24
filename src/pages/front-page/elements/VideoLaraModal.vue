<template>
  <transition name="modal-fade">
    <div class="modal-backdrop">
      <div class="modal-container" role="dialog" aria-labelledby="modalTitle" aria-describedby="modalDescription">

        <div class="modal-sub-container">

          <section class="modal-video">
            <slot name="video">
              <div
                  style="padding:56.25% 0 0 0;
                  position:relative;">
                <iframe
                    id="iframe-video"
                    v-bind:src="videoLink"
                    style="position:absolute;top:0;left:0;width:100%;height:100%;"
                    frameborder="0"
                    allow="autoplay; fullscreen;"
                    allowfullscreen></iframe>
              </div>
            </slot>
          </section>

          <section class="modal-text">
            <slot name="text">
              <div class="text">
                Zur Einleitung unseres Projektes möchten wir drei Positionen vorstellen, die innerhalb des künstlerischen Feldes arbeiten, das uns interessiert. In Form von Video-Interviews, die die Künstler:innen inhaltlich selbst gestalten durften, geben sie uns einen Einblick in ihre künstlerische Praxis und Gedanken, die sie in Hinblick auf das digitale Ausstellen oder die Begehung virtueller Räume haben. Ihre Herangehensweisen und Erfahrungen in diesem Bereich fallen ganz unterschiedlich aus. Im Gespräch war Hold Hands mit den Künstler:innen Paula Abalos, Lara Dâmaso und Mickey Yang. Jede Woche werden wir auf unserer Website ein neues Interview veröffentlichen, um uns den Fragen der Residenz—zeitlich sowie inhaltlich—immer mehr zu nähern.
              </div>
            </slot>
          </section>

          <section class="modal-bio" v-if="smallScreen">
            <slot name="bio">
              <div class="bio">
                Lara Dâmaso (geb. 1996) arbeitet und lebt in Zürich. Nach einer mehrjährigen intensiven Ausbildung in Ballett und zeitgenössischem Tanz, studierte sie an der Hochschule für Grafik und Buchkunst in Leipzig im Fachbereich Medienkunst und an der Zürcher Hochschule der Künste, ZHDK, wo sie ihren Bachelor of Fine Arts erwarb. Ihre künstlerische Praxis variiert zwischen Performances, Videos, Auftritten als Performerin für verschiedene Künstler:innen und DJ-Sets. Lara's Arbeit balanciert zwischen fokussierter Kontrolle und sinnlichem Chaos. Sie strukturiert, um zu destrukturieren und eröffnet so intime Räume, in denen ein Dialog stattfinden kann. Ihre Arbeiten wurden in verschiedenen Institutionen und Off-Spaces gezeigt, wie dem Istituto Svizzero, Centre d'Art Contemporain Genève, Kunsthalle Zürich, Cabaret Voltaire, Plymouth Rock, Kunsthalle Bern, Centre Pasqu'Art. Sie wurde für den Kiefer-Hablitzel Göhner Kunstpreis 2020 nominiert und ist nominiert für die Plattform21. Als Performerin arbeitete sie mit und für Isabel Lewis, Nile Koetting, Nikima Jagudajev, Dora Garcia, Cally Spooner/Offshore, Debora Delmar corp. und Alicia Frankovich.
              </div>
            </slot>
          </section>

        </div>

        <section class="modal-bio" v-if="!smallScreen">
          <slot name="bio">
            <div class="bio">
              Lara Dâmaso (geb. 1996) arbeitet und lebt in Zürich. Nach einer mehrjährigen intensiven Ausbildung in Ballett und zeitgenössischem Tanz, studierte sie an der Hochschule für Grafik und Buchkunst in Leipzig im Fachbereich Medienkunst und an der Zürcher Hochschule der Künste, ZHDK, wo sie ihren Bachelor of Fine Arts erwarb. Ihre künstlerische Praxis variiert zwischen Performances, Videos, Auftritten als Performerin für verschiedene Künstler:innen und DJ-Sets. Lara's Arbeit balanciert zwischen fokussierter Kontrolle und sinnlichem Chaos. Sie strukturiert, um zu destrukturieren und eröffnet so intime Räume, in denen ein Dialog stattfinden kann. Ihre Arbeiten wurden in verschiedenen Institutionen und Off-Spaces gezeigt, wie dem Istituto Svizzero, Centre d'Art Contemporain Genève, Kunsthalle Zürich, Cabaret Voltaire, Plymouth Rock, Kunsthalle Bern, Centre Pasqu'Art. Sie wurde für den Kiefer-Hablitzel Göhner Kunstpreis 2020 nominiert und ist nominiert für die Plattform21. Als Performerin arbeitete sie mit und für Isabel Lewis, Nile Koetting, Nikima Jagudajev, Dora Garcia, Cally Spooner/Offshore, Debora Delmar corp. und Alicia Frankovich.
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
    </div>
  </transition>
</template>

<script>
export default {
  name: "VideoBoxModal",
  data: function () {
    return {
      videoLink: "https://player.vimeo.com/video/510192281?title=0&byline=0&portrait=0",
      smallScreen: false
    }
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

.bio, .text {

  padding: 20px;
  font-size: 12pt;
  color: white;
flex: 1;
overflow: auto;
  /* for Firefox */
  min-height: 0;
}

.bio {
  padding-top: 17%;
}



.modal-container {
  position: absolute;
  width: 89vw;
  height: 89vh;
  background: #FFFFFF;
  box-shadow: 2px 2px 20px 1px;

  display: flex;
  flex-direction: row;
}

.modal-sub-container {
  display: flex;
  flex: 3;
  flex-direction: column;
}

.modal-text {
  flex: 1;
  display: flex;
  background: blue;
  overflow: auto;
}

.modal-video {

  background: gray;
}

.modal-bio {
  flex: 1;
  display: flex;
  background: midnightblue;

}

.modal-backdrop {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: rgba(0, 0, 0, 0.3);
  display: flex;
  justify-content: center;
  align-items: center;
}

.btn-close {
  cursor: pointer;
  height: 6%;
  width: 6%;
  position: absolute;
  right: 0px;
  color: white;
  background: blue;
  border: 0px solid #4AAE9B;
}
</style>
