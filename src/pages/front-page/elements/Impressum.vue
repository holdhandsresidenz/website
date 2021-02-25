<template>
  <DraggableLink
      height="100"
      width="100"
  >
    <div class="box" v-on:click="$emit('clicked', ['impressum'])">
      <div class="icon"></div>
    </div>
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
.icon{
   background: url("../../../assets/Impressum.png") ;
  height: 100%;
  width: 100%;
  background-size: cover;
}
</style>
