<template>
  <draggable-link
      height="80"
      width="90"
  >

<div class="box" v-on:click="$emit('clicked', ['video1'])">
  <div v-bind:class="boxContent" >
    Hallo Test Text Video Beschreibung Halloo
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
border-radius: 0.1em;
  transition-duration: 0.2s;
}
.textBox {
width: 100%;
  height: 100%;
  border-radius: inherit;
  word-wrap: break-word; /* IE 5.5-7 */
  white-space: -moz-pre-wrap; /* Firefox 1.0-2.0 */
  font-size: 11pt;
  color: white;
  background: rgba(0,0,0,0);
  transition-duration: 0s;
  text-shadow: 0 0 12px blue;

}
.pictureBox {
  width: 100%;
  height: 100%;
  border-radius: inherit;
  background-image: url("../../assets/mj.jpg");
  background-size: contain;
  box-shadow: 0 0 14px 0 #010DFF;
  word-wrap: break-word; /* IE 5.5-7 */
  white-space: -moz-pre-wrap; /* Firefox 1.0-2.0 */
  font-size: 16px;
  color: rgba(0,0,0,0);
  transition-duration: 0.2s;
}


</style>
