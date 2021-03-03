<template>
 <div class="outer" v-bind:id="id" >
   <DraggableLink
       v-bind:height="h"
       v-bind:width="w"
       v-bind:id="draggableID"
   >
   <button
       type="button"
       class="btn-open"
       v-bind:style="opnBtnStyle"
       @click="open"
       aria-label="Open Modal"
   >
     <slot name="button-open-modal"></slot>
   </button>
   </DraggableLink>
   <div class="background" v-bind:id="id" v-if="visible">
     <div class="container" role="dialog" aria-labelledby="modalTitle" aria-describedby="modalDescription">
       <slot name="content"></slot>
       <button
           type="button"
           class="btn-close"
           @click="close"
           aria-label="Close modal"
       >
         Close
       </button>
     </div>
   </div>
 </div>

</template>

<script>
import DraggableLink from "@/components/DraggableLink";
export default {
  name: "ModalBoxWButton",
  components: {DraggableLink},
  props: {
    id: String,
    openButtonStyle: Object
},
  data: function () {
    return {
      visible: false,
      smallScreen: false,
      }
  },
  methods: {
    close: function() {
      this.visible = false;
    },
    open: function() {
      this.visible = true;
    }
  },
  computed: {
    opnBtnStyle: function() {
      return this.openButtonStyle
},
    h: function () {
      let h = this.opnBtnStyle.height.split('%');
      h = h[0];
      h = h.split('p');
      h = h[0];
      return h;
    },
    w: function () {
      let h = this.opnBtnStyle.width.split('%');
      h = h[0];
      h = h.split('p');
      h = h[0];
      return h;
    },
    draggableID: function () {
      return "draggable" + this.id;
    }
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
  padding: 0;
  height: 0;
  width: 0;
}
.btn-open {
  border: 0;
  cursor: pointer;
}
.container {
position: relative;
  display: flex;
  width: 89%;
  height: 89%;
  background: #b2b2b2;
  border-radius: 22px ;
  z-index: 12;
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
  top: 0;
  right: 0;
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
