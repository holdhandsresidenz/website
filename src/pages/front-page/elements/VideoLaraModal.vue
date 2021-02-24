<template>
  <transition name="modal-fade">
    <div class="modal-backdrop">
      <div class="modal" role="dialog" aria-labelledby="modalTitle" aria-describedby="modalDescription">

        <div class="modal-sub-container">

          <section class="modal-video">
            <slot name="video">
              <div
                  style="padding:56.25% 0 0 0;
                  position:relative;">
                <iframe
                    src="https://player.vimeo.com/video/510192281?title=0&byline=0&portrait=0"
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
                Text
              </div>
            </slot>
          </section>

        </div>

        <section class="modal-bio">
          <slot name="bio">
            <div class="bio">
              Bio
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
  methods: {
    close() {
      this.$emit('close');
    },
  },
}
</script>

<style scoped>
*{
  margin: 0;
  padding: 0;
}
.bio, .text {
  font-size: 16pt;
  color: white;
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

.modal {
  position: absolute;
  width: 89vw;
  height: 89vh;
  background: #FFFFFF;
  box-shadow: 2px 2px 20px 1px;
  overflow-x: auto;
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
}

.modal-sub-container {
  display: flex;
  flex: 3;
  flex-direction: column;
  justify-content: space-between;
  align-content: stretch;
}

.modal-text {
  top: 0;
  height: 100%;
  background: blue;
}

.modal-video {
  top: 0;
  background: gray;
}

.modal-bio {
  flex: 1;
  background: midnightblue;
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
