<template>
  <DraggableLink
      id="draggable-link-impressum"
  >
      <div class="icon-impressum" v-on:click="$emit('clicked', ['impressum'])"></div>
  </DraggableLink>
</template>

<script>
import DraggableLink from "@/components/DraggableLink";
export default {
  name: "ImpressumIcon",
  components: {
    DraggableLink
  }
}
</script>

<style scoped>

.icon-impressum{
  background: url("../../../../assets/Impressum.png") no-repeat;
  height: 7vw;
  width: 6vw;
  background-size: cover;
}
@media all and (max-width: 1000px) {

  .icon-impressum {
    height: 100px;
    width: 95px;
  }

}
</style>
