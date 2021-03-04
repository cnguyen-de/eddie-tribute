<template>
  <div class="min-h-screen w-screen bg-gray-900 grid place-items-center text-3xl text-white">
    <Hero />
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component'
import Hero from './components/Hero.vue'

@Options({
  components: {
    Hero
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
