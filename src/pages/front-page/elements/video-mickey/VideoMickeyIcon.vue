<template>
  <draggable-link
    id="videoMickeyIcon"
  >

    <div class="box" v-on:click="$emit('clicked', ['video-mickey'])">
      <div v-bind:class="boxContent" >
        <p>
          INTERVIEW <br/> MICKEY YANG
        </p>
      </div>
    </div>
  </draggable-link>
</template>

<script>
import DraggableLink from "@/components/DraggableLink";
export default {
  name: "VideoMickeyIcon",
  components: {
    DraggableLink,
  },
  data: function () {
    return {
      boxContent: "pictureBox"
    }
  },
  methods: {
    switchContent: function () {
      setInterval(()=>
              this.boxContent = ((this.boxContent==="pictureBox") ?  "textBox" : "pictureBox")
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
  user-select: none;

  word-wrap: break-word; /* IE 5.5-7 */
  white-space: -moz-pre-wrap; /* Firefox 1.0-2.0 */
  font-family: Narr, sans-serif;
  color:#1e4650;
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
  background: url("../../../../assets/mickey-form-web.png") no-repeat;
  background-size: contain;
  color: rgba(0,0,0,0);
  font-family: Narr, sans-serif;
}

@media all and (max-width: 1000px) {
  .textBox {
    width: 150px;
    height: 150px;
    font-size: 16pt;
    line-height: 150%;
  }
  .pictureBox {
    width: 200px;
    height: 200px;
  }

}
</style>

