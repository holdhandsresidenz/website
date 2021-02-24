<template>
  <vue-draggable-resizable
      v-bind:w = "width"
      v-bind:h = "height"
      :draggable="true"
      :resizeable:="false"
      @dragging="onDrag"
      @dragstop="dragEnd"
  >

    <a
        v-bind:target="target"
        v-bind:href="link"
        v-bind:download="download"
        v-bind:class="{linkEnabled : this.notDragging, linkDisabled: !this.notDragging}"
    >
 <slot></slot>
    </a>
  </vue-draggable-resizable>
</template>

<script>
export default {
name: "DraggableLink",
  props : {
  width: [String,Number],
    height: [String,Number],
  link: String,
    target: String,
    download: String
  },
  data: function () {
    return {
      notDragging: true
    }
  },
  methods: {
    onDrag: function (){
      this.notDragging = false;
    },
    dragEnd: function () {
      this.notDragging = true;
    }
  }
}
</script>

<style scoped>
* {
  user-select: none;
  -moz-user-select: none;
  -khtml-user-select: none;
  -webkit-user-select: none;
  -o-user-select: none;
}
.linkEnabled {
  pointer-events: all;
}
.linkDisabled {
  pointer-events: none;
}

@media all and (max-width: 1000px) {
  * {
    user-select: none;
    -moz-user-select: none;
    -khtml-user-select: none;
    -webkit-user-select: none;
    -o-user-select: none;
  }
  .linkEnabled {
    pointer-events: all;
  }
  .linkDisabled {
    pointer-events: none;
  }

}
</style>
