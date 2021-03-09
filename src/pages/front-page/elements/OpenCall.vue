<template>
  <draggable-link
      id="opencallIcon"
      link='../assets/opencall-holdhands-de.pdf'
      target="_blank"
      download="opencall-holdhands-de.pdf"
  >
    <img id="pdf-thumb" src="@/assets/opencall-pdf-icon.png">

  </draggable-link>

</template>

<script>


import DraggableLink from "@/components/DraggableLink";

export default {
  name: "OpenCall",
  components: {DraggableLink},
}

</script>

<style scoped>

#pdf-thumb {
  height: 7vw;
}

@media all and (max-width: 1000px) {
  a {
    position: relative;
    width: 100vw;
    height: 50vw;
  }
  #pdf-thumb {
    height: 100px;
  }

}
</style>
