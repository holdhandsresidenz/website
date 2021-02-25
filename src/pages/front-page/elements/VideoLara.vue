<template>
  <draggable-link
      height="250"
      width="250"
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
  font-size: 19pt;

  font-family: Narr;
  color: #ffffff;
}

.textBox {
  width: 100%;
  height: 100%;
  padding-left: 15%;
  padding-top: 12%;
  border-radius: inherit;
  background: rgba(0,0,0,0);
  transition-duration: 0s;
}

.pictureBox {
  width: 100%;
  height: 100%;
  border-radius: inherit;
  background: url("../../../assets/lara-form-web.png") no-repeat;
  background-size: contain;
  color: rgba(0,0,0,0);

}

</style>
