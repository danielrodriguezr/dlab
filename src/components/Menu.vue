<template>
<header id="menu">
    <!-- <h1 id="logo">drr.lab</h1> -->
    <img src="~@/assets/logo.png" alt="" id="logo">
    <ul>
      <li><a href="#BW">BW</a></li>
      <li><a href="#Colors">Colors</a></li>
    </ul>
  </header>
</template>

<script>
export default {
  name: 'Menu',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

#menu {
  height: 100vh;
  padding-left: 5vw;
  position: fixed;
  z-index: 100;
  display: flex;
  pointer-events: none;
  scroll-behavior: smooth;
}
#logo {
  position: absolute;
  max-height: 100px;
  top: 10px;
}
#menu ul {
  height: 80%;
  display: flex;
  flex-wrap: wrap;
  align-content: center;
  margin: auto;
  border-style: solid;
  border-radius: 0 0 0 100px;
  border-width: 0px 0px 1px 3px;
}
#menu ul li {
  width: 100%;
  font-size: 1.5rem;
  pointer-events:all;

}
</style>
