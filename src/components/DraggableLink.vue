<template>
  <vue-draggable-resizable
      v-bind:id="id"

      :draggable="true"
      :resizeable:="false"
      :handles="[]"
      @dragging="onDrag"
      @dragstop="dragEnd"
  >
    <a  v-bind:id="linkId"
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
    download: String,
    id: String
  },
  data: function () {
    return {
      notDragging: true,
      cHeight: 100,
      cWidth: 100
    }
  },
  computed: {
    linkId: function () {
      return this.id + "-a"
    }
  },
  methods: {
    onDrag: function (){
      this.notDragging = false;
    },
    dragEnd: function () {
      this.notDragging = true;
    },
    setCWidth: function () {
      this.cWidth =  document.getElementById(this.linkId).offsetWidth
    },
    setCHeight: function () {

      this.cHeight =  document.getElementById(this.linkId).offsetHeight
    },

  },
  mounted() {
  this.setCHeight()
    this.setCWidth()
  }
}
</script>

<style scoped>

* {

  cursor: pointer;
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

</style>
