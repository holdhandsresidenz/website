<template>
  <draggable-link
      height="80"
      width="90"
  >
    <button
        type="button"
        class="btn"
        @click="showModal"
    >
      Open Modal!
    </button>

    <VideoBoxModal
        v-show="isModalVisible"
        @close="closeModal"
    />
<div class="box">
  <div v-bind:class="boxContent" >
    Hallo Test Text Video Beschreibung Halloo
  </div>

</div>
  </draggable-link>
</template>

<script>
import DraggableLink from "@/shared/DraggableLink";
import VideoBoxModal from "@/shared/VideoBoxModal";

export default {
  name: "VideoBox",
  components: {
    DraggableLink,
    VideoBoxModal
  },
  data: function () {
    return {
     boxContent: "textBox",
      isModalVisible: false,
    }
  },
  methods: {
    showModal() {
      this.isModalVisible = true;
    },
    closeModal() {
      this.isModalVisible = false;
    },
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
.modal-mask {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: table;
  transition: opacity 0.3s ease;
}

.modal-wrapper {
  display: table-cell;
  vertical-align: middle;
}

.modal-container {
  width: 300px;
  margin: 0px auto;
  padding: 20px 30px;
  background-color: #fff;
  border-radius: 2px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.33);
  transition: all 0.3s ease;
  font-family: Helvetica, Arial, sans-serif;
}



.box {
  height: 100%;
  width: 100%;

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
  background-image: url("../assets/mj.jpg");
  background-size: contain;
  box-shadow: 0 0 14px 0 #010DFF;
  word-wrap: break-word; /* IE 5.5-7 */
  white-space: -moz-pre-wrap; /* Firefox 1.0-2.0 */
  font-size: 16px;
  color: rgba(0,0,0,0);
  transition-duration: 0.2s;
}






</style>
