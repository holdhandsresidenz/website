<template>
    <div class="background">
      <div class="container" role="dialog" aria-labelledby="modalTitle" aria-describedby="modalDescription" id="container">
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
* {
  z-index: 999;
}
.container {
  position: fixed;

  width: 89%;
  height: 89%;
  background: rgba(62,42,51,0);
  display: flex;
  border-radius: 22px ;
}

.background {
  position: fixed;
  width: 100%;
height: 100%;
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
z-index: 1000;
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
    width: 100%;
    height: 100%;
  }
  .container::-webkit-scrollbar {
    width: 0px;
  }
  .background {
    background-color: black;
  }
  .btn-close {
    top: 0vh;
    right: 0vw;
  }
}
</style>
