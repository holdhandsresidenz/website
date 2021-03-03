<template>
  <DraggableLink
      height="100"
      width="100"
      id="draggable-link-impressum"
  >
      <div class="icon-impressum" v-on:click="$emit('clicked', ['impressum'])"></div>
  </DraggableLink>
</template>

<script>
import DraggableLink from "@/components/DraggableLink";
export default {
  name: "Impressum",
  components: {
    DraggableLink
  }
}
</script>

<style scoped>
.box {
  height: 100%;
  width: 100%;
}
.icon-impressum{
  background: url("../../../../assets/Impressum.png") ;
  height: 100%;
  width: 100%;
  background-size: cover;
}
</style>
