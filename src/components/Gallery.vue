<template>
  <div class="gallery grid grid-cols-2 gap-4 md:grid-cols-4">
    <figure v-for="let img of imgList">
      <img :src="img" alt="" />
    </figure>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component'
import { loadAll } from 'js-yaml'

@Options({})
export default class Gallery extends Vue {
    imgList =
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
