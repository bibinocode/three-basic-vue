<template>
  <div class="scene" ref="sceneRef">
  </div>
</template>

<script setup>
import { onMounted, ref } from 'vue'
import * as Three from 'three'
import scene from '@/three/scene'
import camera from '@/three/camera'
import renderer from '@/three/renderer'
import animate from '@/three/animate'
import axes from '@/three/aexHelper'
import controls from '@/three/controls'
import createCity from '@/three/mesh/city'
import '@/three/init'


const sceneRef = ref(null)
scene.add(camera)
scene.add(axes)
createCity()
onMounted(() => {
  sceneRef.value.appendChild(renderer.domElement)
  animate()
})


</script>

<style lang="scss">
.scene {
  height: 100vh;
  width: 100vw;
  position: fixed;
  z-index: 100;
  left: 0;
  top: 0;
}
</style>