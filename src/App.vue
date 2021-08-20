<template>
<Menu></Menu>
<div id="main-container">
  <Galeria></Galeria>
</div>
<Fondo></Fondo>
</template>

<script>
import Menu from './components/Menu.vue'
import Galeria from './components/Galeria.vue'
import Fondo from './components/Fondo.vue'

export default {
  name: 'App',
  components: {
    Menu,
    Galeria,
    Fondo
  }
}

</script>

<style>
@font-face {
  font-family: "CHANEY regular";
  src: url("./fonts/CHANEY-Regular.woff");
}
@font-face {
  font-family: "CHANEY extended";
  src: url("./fonts/CHANEY-Extended.woff");
}
@font-face {
  font-family: "CHANEY wide";
  src: url("./fonts/CHANEY-Wide.woff");
}
@font-face {
  font-family: "CHANEY ultraextended";
  src: url("./fonts/CHANEY-UltraExtended.woff");
}
</style>

