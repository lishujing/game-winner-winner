<script setup lang="ts">
import { onMounted } from 'vue'

let canvas = null
let pacmanFrames = null
let ghostFrames = null
let canvasContext = null

onMounted(() => {
  canvas = document.getElementById('pacmanCanvas')
  canvasContext = canvas.getContext("2d")
  pacmanFrames = document.getElementById("pacmanAnimation");
  ghostFrames = document.getElementById('pacmanGhosts')
})

let createRect = ( x, y, width, height, color ) => {
  canvasContext.fillStyle = color;
  canvasContext.fillRect(x, y, width, height)
}

</script>

<template>
  <div class="pacman-container">
    <canvas id="pacmanCanvas" class="pacman-canvas"></canvas>
    <div style="display:none;">
      <img id="pacmanAnimation" src="@/assets/image/animations.gif" width="140" height="20" />
      <img id="pacmanGhosts" src="@/assets/image/ghost.png" width="140" height="20" />
    </div>
  </div>
</template>

<style scoped>
.pacman-container{
  width: 100vw;
  height: 100vh;
  overflow: hidden;
  background-color: black;
}
.pacman-canvas{
  width: 500px;
  height: 500px;
}
</style>
