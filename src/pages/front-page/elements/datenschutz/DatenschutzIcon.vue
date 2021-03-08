<template>
  <DraggableLink
      id="datenschutzIcon"

  >
      <div class="icon-datenschutz" v-on:click="$emit('clicked', ['datenschutz'])"></div>
  </DraggableLink>
</template>

<script>
import DraggableLink from "@/components/DraggableLink";
export default {
  name: "DatenschutzIcon",
  components: {
    DraggableLink
  }
}
</script>

<style scoped>

.icon-datenschutz{
  background: url("../../../../assets/Datenschutz.png") no-repeat;

  height: 7vw;
  width: 6vw;
  background-size: cover;
}
</style>
