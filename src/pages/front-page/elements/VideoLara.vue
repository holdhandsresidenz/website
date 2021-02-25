<template>
  <draggable-link
      height="80"
      width="90"
  >

<div class="box" v-on:click="$emit('clicked', ['video1'])">
  <div v-bind:class="boxContent" >
    Interview <br/> Lara Dâmaso
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
      , 1000);
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
  font-size: 12pt;
  color: #B9BABB;

}

.textBox {
  width: 100%;
  height: 100%;
  border-radius: inherit;
  transform: skewY(12deg) rotate(-12deg);

  background: rgba(0,0,0,0);
  transition-duration: 0s;
  text-shadow: 0 0 3px gray;
}

.pictureBox {
  width: 100%;
  height: 100%;
  border-radius: inherit;

  background: url("../../../assets/blob.svg") no-repeat;
  background-size: contain;

  color: rgba(0,0,0,0);
  transition-duration: 0.2s;
}


</style>
