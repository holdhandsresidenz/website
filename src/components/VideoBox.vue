<template>
    <draggable-link
        class="videoBox"
        height="80"
        width="80"
    >

      <div class="switchingContent">
        agha gjsd 9dja lklaö agajlk gjkdfgjk a
      </div>

    </draggable-link>
  </template>

<script>
import DraggableLink from "@/shared/DraggableLink";
export default {
name: "VideoBox",
  components: {
  DraggableLink
  }
}
</script>

<style scoped>
.videoBox {
  background: #2c3e50;
  position: absolute;

  word-wrap: break-word;      /* IE 5.5-7 */
  white-space: -moz-pre-wrap; /* Firefox 1.0-2.0 */

  font-size-adjust: 0.12;
  box-shadow: 0px 0px 15px 0px white;
}

.switchingContent {
box-sizing: border-box;

  background-size: contain; background-position: center;

animation-name: switch;
  animation-iteration-count: infinite;
  animation-duration: 4s;
  animation-direction: alternate;
}

.glowing {
  animation-name: glow;
  animation-iteration-count: infinite;
  animation-duration: 2s;
  animation-direction: alternate;
}
@keyframes glow {
  0% {box-shadow: 0px 0px 15px 0px white;}
  100% {box-shadow: 0px 0px 10px 0px royalblue;}
}
@keyframes switch {
  0% {color: black;  opacity: 100%; background: rgba(0,0,0,0)}
  33% {color: black; opacity: 100%; background: rgba(0,0,0,0)}
  50% {opacity: 0%; color: rgba(0,0,0,0); background: rgba(0,0,0,0); background-size: contain; background-position: center }
  66% {opacity: 100%;color: rgba(0,0,0,0); background: url("../assets/mj.jpg") no-repeat; background-size: contain; background-position: center}
  100% {opacity: 100%;color: rgba(0,0,0,0); background: url("../assets/mj.jpg") no-repeat; background-size: contain; background-position: center}

}

</style>
