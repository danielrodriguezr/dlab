<template>
  <Renderer ref="renderer" antialias :pointer="{ onMove: onPointerMove }" resize :orbit-ctrl="{ enableDamping: true }">
    <Camera :position="{ x: 0, y: 0, z: 20 }" />
    <Scene ref="scene" background="#ff0000">
     <RefractionMesh ref="mesh" :position="{ x: 0, y: -20, z: 20 }" auto-update>
        <Sphere :radius="4" />
        <StandardMaterial color="#ffffff" :props="{ metalness: 1, roughness: 0, flatShading: false }" />
      </RefractionMesh>
    </Scene>
  </Renderer>
</template>

<script>
import {
  Camera,
  Renderer,
  Scene,
  StandardMaterial,
  Sphere
} from 'troisjs';
export default {
  components: {
    Camera,
    Renderer,
    Scene,
    StandardMaterial,
    Sphere
  },
  setup() {
    return {
      WIDTH: 30,
      HEIGHT: 30,
    };
  },
  data() {
    return {
     
    };
  },
  mounted() {
  },
  unmounted() {
  },
  methods: {
  },
};
</script>

<style>
canvas {
  height: 100vh;
}
</style>