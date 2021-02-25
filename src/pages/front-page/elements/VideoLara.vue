<template>
  <draggable-link
      height="250"
      width="250"
  >

<div class="box" v-on:click="$emit('clicked', ['video1'])">
  <div v-bind:class="boxContent" >
    INTERVIEW <br/> LARA DÂMASO
  </div>
</div>
  </draggable-link>
</template>

<script>
import DraggableLink from "@/components/DraggableLink";
export default {
  name: "VideoBox",
  components: {
    DraggableLink,
  },
  data: function () {
    return {
     boxContent: "textBox"
    }
  },
  methods: {
    switchContent: function () {
      setInterval(()=>
              this.boxContent = ((this.boxContent==="textBox") ? "pictureBox" : "textBox")
          // Jede sekunde
      , 1500);
    }
  },
  mounted() {
    this.switchContent();
  }
}
</script>

<style scoped>

.box {
  height: 100%;
  width: 100%;
  cursor: pointer;
  border-radius: 0.3em;
  transition-duration: 0.2s;
  user-select: none;

  word-wrap: break-word; /* IE 5.5-7 */
  white-space: -moz-pre-wrap; /* Firefox 1.0-2.0 */
  font-size: 19pt;
  word-spacing: 0.25em;
  font-family: Narr, sans-serif;
  color:#1e4650;
}

.textBox {
  width: 100%;
  height: 100%;
  padding-left: 15%;
  padding-top: 12%;
  border-radius: inherit;
  background: rgba(0,0,0,0);
  transition-duration: 0s;
  font-family: Narr, sans-serif;

}

.pictureBox {
  width: 100%;
  height: 100%;
  border-radius: inherit;
  background: url("../../../assets/lara-form-web.png") no-repeat;
  background-size: contain;
  color: rgba(0,0,0,0);
  font-family: Narr, sans-serif;
}

@media all and (max-width: 1000px) {
  .box {

    font-size: 16pt;

  }

}
</style>
