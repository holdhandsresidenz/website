<template>

    <a
        target="_blank"
        href="../assets/opencall-holdhands-de.pdf">
      <img id="pdf-thumb" src="../assets/opencall-pdf-icon.png">
    </a>

</template>

<script>
export default {
name: "OpenCall"
}
</script>

<style scoped>
a {
  position: relative;
  float: left;
  width: 35vw;
  height: 35vw;
  padding-top: 31vh;
  padding-left: 2vw;
}
#pdf-thumb{
  height: 100px;
}

@media all and (max-width: 1000px) {
  a {
    position: relative;
    width: 100vw;
    height: 50vw;
    margin-top: 30vh;
    padding-left: 22vw;
  }
  #pdf-thumb{
    height: 300px;
  }
}
</style>
