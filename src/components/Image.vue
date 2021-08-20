<template>
   <slot></slot>
   <img v-for="image in gallery.images" :src="image.url" :alt="image.url" :key="image"/>
</template>