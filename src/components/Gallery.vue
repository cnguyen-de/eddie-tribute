<template>
  <div class="gallery grid grid-cols-2 gap-4 md:grid-cols-4">
    <figure v-for="img of images" :key="img">
      <img class="h-64 w-64" :src="img.url" alt="" />
      {{ img.url }}
    </figure>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component'
import { loadAll } from 'js-yaml'
// eslint-disable-next-line no-unused-vars
import { EddieImage } from '../model/EddieImage'
import axios from 'axios'

@Options({})
export default class Gallery extends Vue {
  imgList: EddieImage[] = []
  created() {
    axios.get('https://raw.githubusercontent.com/cnguyen-de/eddie-tribute/master/data.yml').then(res => {
      this.imgList = loadAll(res.data)
      console.log(loadAll(res.data))
    })
  }

  get images() {
    return this.imgList
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
