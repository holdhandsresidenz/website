<template>
  <vue-draggable-resizable
      :w="100"
      :h="100"
      :draggable="true"
      :resizeable:="false"
      @dragging="onDrag"
      :onDragStart="dragStart"
      @dragstop="dragEnd"
  >
    <a
        target="_blank"
        href="../assets/opencall-holdhands-de.pdf"
        v-bind:class="{linkEnabled : this.notDragging, linkDisabled: !this.notDragging}"
    >
      <img id="pdf-thumb" src="../assets/opencall-pdf-icon.png">
    </a>

  </vue-draggable-resizable>

</template>

<script>


export default {
name: "OpenCall",
  data: function () {
  return {
    notDragging: true
  }
  },
  computed: {
  },
  methods: {
  onDrag: function (){
    this.notDragging = false;
    console.log("On Drag")
  },
  dragStart: function () {
    console.log("Started");
  },
  dragEnd: function () {
    this.notDragging = true;
    console.log("Ended")
  }
  }


}

</script>

<style scoped>
a {

  float: left;
  padding-top: 30vh;
  padding-left: 15vw;
}

.linkEnabled {
  pointer-events: all;
}
.linkDisabled {
  pointer-events: none;
}

#pdf-thumb{
  height: 100px;
}

@media all and (max-width: 1000px) {
  a {
    position: relative;
    width: 100vw;
    height: 50vw;

  }
  .linkEnabled {
    pointer-events: all;
  }
  .linkDisabled {
    pointer-events: none;
  }
  #pdf-thumb{
    height: 300px;
  }
}
</style>
