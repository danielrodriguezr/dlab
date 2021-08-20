<template>
<div id="main-container">
  <div class="row" v-for="gallery in galleries" :key="gallery" :id="gallery.name">
    <div class="gallery">
      <img v-for="image in gallery.images" :src="image.url" :alt="image.url" :key="image"/>
    </div>
  </div>
</div>
</template>

<script>
export default {
  data() {
    return {
      galleries: [
        {
          name: "BW", 
          images: [
            {url: "img/morado.jpg"},
            {url: "img/morado.jpg"},
            {url: "img/morado.jpg"}
          ]
        },
        {
          name: "Colors", 
          images: [
            {url: "img/sorcha.jpg"},
            {url: "img/sorcha.jpg"},
            {url: "img/sorcha.jpg"}
          ]
        }
      ]
    }
  },
  mounted() {
    const slider = document.getElementsByClassName('gallery');
    console.log(slider);
    let mouseDown = false;
    let startX, scrollLeft;

    slider.forEach(element => { 
      let startDragging = function (e) {
        mouseDown = true;
        startX = e.pageX - element.offsetLeft;
        scrollLeft = element.scrollLeft;
      };
      let stopDragging = function () {
        mouseDown = false;
      };
    element.addEventListener('mousemove', (e) => {
      e.preventDefault();
      
      if(!mouseDown) { return; }
      const x = e.pageX - element.offsetLeft;
      const scroll = x - startX;
      element.scrollLeft = scrollLeft - scroll;
    });  
      element.addEventListener('mousedown', startDragging, false);
      element.addEventListener('mouseup', stopDragging, false);
      element.addEventListener('mouseleave', stopDragging, false);
    });
  },
}
</script>

<style lang="css">
  #main-container {
  height: 100vh;
  width: 100vw;
  min-height: 600px;
  position: fixed;
  overflow: auto;
  scroll-behavior: smooth;
  z-index: 90;
}

#main-container .row {
  height: 100%;
  width: 100%;
  display: flex;
  background-size: cover;
  background-attachment: fixed;
}

.gallery {
  height: 600px;
  width: 100%;
  overflow-x: auto;
  margin: auto;
  display: flex;
  z-index: 2;
  scroll-behavior: smooth;
}
.gallery::-webkit-scrollbar{
  display: none;
}
.gallery img {
  border-radius: 20px;
  margin: 50px;
  max-width: 100%;
  object-fit: cover;

}
</style>