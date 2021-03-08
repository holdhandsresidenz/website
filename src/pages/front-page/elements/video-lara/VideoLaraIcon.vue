<template>
  <draggable-link
  id="videoLaraIcon"
  >

<div class="box" v-on:click="$emit('clicked', ['video1'])">
  <div v-bind:class="boxContent" >
    <p>INTERVIEW <br/> LARA DÂMASO</p>
  </div>
</div>
  </draggable-link>
</template>

<script>
import DraggableLink from "@/components/DraggableLink";
export default {
  name: "VideoLaraIcon",
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
  cursor: pointer;
  border-radius: 0.3em;
  transition-duration: 0.2s;
  user-select: none;

  word-wrap: break-word; /* IE 5.5-7 */
  white-space: -moz-pre-wrap; /* Firefox 1.0-2.0 */

  word-spacing: 0.25em;
  font-family: Narr, sans-serif;
  color:#1e4650;
  background: rgba(0,0,0,0);

}

.textBox {
  font-size: 1.7vw;
  line-height: 2.4vw;
  width: 16vw;
  height: 9vw;

  padding-top: 1vw;
  border-radius: inherit;

}
p{
  padding-left: 9vw;
}
.pictureBox {

  width: 16vw;
  height: 9vw;

  border-radius: inherit;
  background: url("../../../../assets/lara-form-web.png") no-repeat;
  background-size: contain;
  color: rgba(0,0,0,0);
}

@media all and (max-width: 1000px) {
  .box {
    font-size: 16pt;
  }
}
</style>
