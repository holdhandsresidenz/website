<template>

  <div
      id="container"
      aria-describedby="modalDescription"
      aria-labelledby="modalTitle"
      class="container"
      role="dialog"
      v-bind:style="{left: left + 'vw', right: right + 'vw', top: top + 'vw', bottom: bottom +'vw', borderRadius: borderRadius +'vw'}"
  >
    <button
        aria-label="Close modal"
        class="btn-close"
        type="button"
        @click="close"
    >
      Close
    </button>
    <slot></slot>
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
  props: {
    top: String,
    bottom: String,
    left: String,
    right: String,
    borderRadius: String

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
  position: absolute;

  border-radius: 1.4vw;
overflow: hidden;

}

.btn-close {
  position: absolute;
  right: 0;
  font-family: Narr, sans-serif;
  font-size: 1.8vw;
  cursor: pointer;
  height: 2.8vw;

  width: 5.5vw;

  color: #b2b2b2;
  background: #0015ff;
  border: 0;
  border-radius: 1.4vw;

  z-index: 1000;
}

@media all and (max-width: 1000px) {

}
</style>
