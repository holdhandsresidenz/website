<template>
  <draggable-link
      link='../assets/opencall-holdhands-de.pdf'
      target="_blank"
      download="opencall-holdhands-de.pdf"
      width="100"
      height="100"
  >
    <img id="pdf-thumb" src="@/assets/opencall-pdf-icon.png">

  </draggable-link>

</template>

<script>


import DraggableLink from "@/shared/DraggableLink";

export default {
  name: "OpenCall",
  components: {DraggableLink},
}

</script>

<style scoped>
a {


}


#pdf-thumb {
  height: 100px;
}

@media all and (max-width: 1000px) {
  a {
    position: relative;
    width: 100vw;
    height: 50vw;
  }

  #pdf-thumb {
    height: 150px;
  }
}
</style>
