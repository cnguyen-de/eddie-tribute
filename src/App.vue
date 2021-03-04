<template>
  <div class="min-h-screen w-screen bg-gray-900">
    <Hero />
    <Gallery />
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component'
import Hero from './components/Hero.vue'
import Gallery from './components/Gallery.vue'

@Options({
  components: {
    Hero,
    Gallery
  }
})
export default class App extends Vue {}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
