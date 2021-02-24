<template>
  <transition name="modal-fade">
    <div class="modal-backdrop">
      <div class="modal"
           role="dialog"
           aria-labelledby="modalTitle"
           aria-describedby="modalDescription"
      >
        <header
            class="modal-text"
            id="modalTitle"
        >
          <slot name="header">
            text
          </slot>
        </header>
        <section
            class="modal-video"
            id="modalDescription"
        >
          <slot name="body">
            Video
          </slot>
        </section>
        <footer class="modal-bio">
          <slot name="footer">
            Bio
          </slot>
        </footer>
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



.modal-text {
  flex: 1;
  background: #533D4A;
}

.modal-bio {
  flex: 1;
  background: #533D4A;
}

.modal-video {
  flex: 2.66;
  background: #010DFF;
}


.btn-close {
  cursor: pointer;
  height: 60px;
  width: 60px;
  position: absolute;
 right: 0px;
  color: white;
  background: blue;
  border: 0px solid #4AAE9B;

}
</style>
