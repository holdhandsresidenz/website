<template>
  <vue-draggable-resizable
      v-bind:w = width
      v-bind:h = height
      :draggable="true"
      :resizeable:="false"
      @dragging="onDrag"
      :onDragStart="dragStart"
      @dragstop="dragEnd"
  >

    <a
        v-bind:target="target"
        v-bind:href="link"
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
  width: String,
    height: String,
  link: String,
    target: String
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
.linkEnabled {
  pointer-events: all;
}
.linkDisabled {
  pointer-events: none;
}

@media all and (max-width: 1000px) {

  .linkEnabled {
    pointer-events: all;
  }
  .linkDisabled {
    pointer-events: none;
  }

}
</style>
