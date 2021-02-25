<template>
  <transition name="modal-fade">
    <div class="modal-backdrop">
      <div class="modal-container" role="dialog" aria-labelledby="modalTitle" aria-describedby="modalDescription" id="container">
        <slot></slot>
      </div>
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
  name: "ModalBox",
  data: function () {
    return {
      smallScreen: false,
      }
  },
  computed: {
    overflow: function () {
      return this.smallScreen ? "auto" : "null"
    },
  },
  methods: {
    close() {
      this.$emit('close');
    },
  },
  mounted() {
    if (screen.width < 1000) {
      this.smallScreen = true;
    }
  }
}
</script>

<style scoped>
.modal-container {
position: fixed;
  width: 89%;
  height: 89%;
  background: #b2b2b2;
display: flex;
  border-radius: 22px ;
}


.modal-backdrop {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: rgba(0, 0, 0, 0.3);
}

.btn-close {
  font-family: Narr, sans-serif;
  font-size: 20pt;
  cursor: pointer;
  height: 40px;
  width: 80px;
  color: #b2b2b2;
  background: #0015ff;
  border: 0;
  border-radius: 22px ;
  position: absolute;
  top: 5.5vh;
  right: 5.5vw;
z-index: 100;

}

@media all and (max-width: 1000px) {
  .greenline {
    z-index: 5555;
    height: 22px;
    margin: 0  22px 0 22px;
    border-radius: 0;
    background: #00ff00;
  }
  .modal-container {
    width: 100%;
    height: 100%;
  }
  .modal-container::-webkit-scrollbar {
    width: 0px;

  }
  .btn-close {
    top: 0vh;
    right: 0vw;
  }
}
</style>
