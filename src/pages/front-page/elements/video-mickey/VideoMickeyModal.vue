<template>
  <ModalBox  @close=close>
    <div class="container">

        <section class="video">
          <div class="framing">
            <iframe
                id="iframe-video-mickey"
                src="https://www.youtube.com/embed/hcq1uCh3VTg"
                frameborder="0"
                allow="autoplay; fullscreen;"
                allowfullscreen></iframe>
            </div>
        </section>
      <div class="greenline" v-if="smallScreen"></div>
        <section class="biographie">
          {{kurzbio}}
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
    kurzbio: "asdklöfjh aösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkösdkljaö afklöajsdfö asödlkfja jasdfölkj aksdjfkasdklöfjh aösdkljaö afklöajsdfö asödlkfja jasdfölkj aksdjfkasdklöfjh aösdkljaö afklöajsdfö asödlkfja jasdfölkj aksdjfkasdklöfjh aösdkljaö afklöajsdfö asödlkfja jasdfölkj aksdjfkasdklöfjh aösdkljaö afklöajsdfö asödlkfja jasdfölkj aksdjfkasdklöfjh aösdkljaö afklöajsdfö asödlkfja jasdfölkj aksdjfkasdklöfjh aösdkljaö afklöajsdfö asödlkfja jasdfölkj aksdjfkasdklöfjh aösdkljaö afklöajsdfö asödlkfja jasdfölkj aksdjfkasdklöfjh aösdkljaö afklöajsdfö asödlkfja jasdfölkj aksdjfkasdklöfjh aösdkljaö afklöajsdfö asödlkfja jasdfölkj aksdjfkasdklöfjh aösdkljaö afklöajsdfö asödlkfja jasdfölkj aksdjfkasdklöfjh aösdkljaö afklöajsdfö asödlkfja jasdfölkj aksdjfkasdklöfjh aösdkljaö afklöajsdfö asödlkfja jasdfölkj aksdjfkasdklöfjh aösdkljaö afklöajsdfö asödlkfja jasdfölkj aksdjfkasdklöfjh aösdkljaö afklöajsdfö asödlkfja jasdfölkj aksdjfkasdklöfjh aösdkljaö afklöajsdfö asödlkfja jasdfölkj aksdjfkasdklöfjh aösdkljaö afklöajsdfö asödlkfja jasdfölkj aksdjfkasdklöfjh aösdkljaö afklöajsdfö asödlkfja jasdfölkj aksdjfkasdklöfjh aösdkljaö afklöajsdfö asödlkfja jasdfölkj aksdjfkasdklöfjh aösdkljaö afklöajsdfö asödlkfja jasdfölkj aksdjfkasdklöfjh aösdkljaö afklöajsdfö asödlkfja jasdfölkj aksdjfkasdklöfjh aösdkljaö afklöajsdfö asödlkfja jasdfölkj aksdjfkasdklöfjh aösdkljaö afklöajsdfö asödlkfja jasdfölkj aksdjfk"
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
    padding: 10px 0px 0px 10px;
    font-size: 12pt;
    color: black;
    overflow: auto;
    background: #b2b2b2;
  }
@media all and (max-width: 1000px) {
    .greenline {
      z-index: 5555;
      height: 22px;
      margin: 0  22px 0 22px;
      border-radius: 0;
      background: #00ff00;
    }
  .container {
    overflow: auto;
  }
  .video {
    flex: unset;
    width: 100%;
    height: 100%;
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
