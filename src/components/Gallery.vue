<template>
  <div class="gallery p-4">
    <div class="gallery-container">
      <figure class="" v-for="img of images" :key="img">
        <img loading="lazy" :src="img.url" alt="" v-if="!img.url.includes('mp4')" />
        <video loading="lazy" controls playsinline autoplay loop :src="img.url" v-if="img.url.includes('mp4')" />
      </figure>
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component'
import { load } from 'js-yaml'
// eslint-disable-next-line no-unused-vars
import { EddieImage } from '../model/EddieImage'
import axios from 'axios'

@Options({})
export default class Gallery extends Vue {
  imgList: any = []
  created() {
    axios.get('https://raw.githubusercontent.com/cnguyen-de/eddie-tribute/master/data.yml').then(res => {
      this.imgList = load(res.data)
      console.log(load(res.data))
    })
  }

  get images() {
    return this.imgList
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.gallery-container {
  column-count: 3;
  column-gap: 16px;
}

figure {
  margin: 0;
  display: grid;
  grid-template-rows: 1fr auto;
  margin-bottom: 16px;
  break-inside: avoid;
}

figure > img {
  grid-row: 1 / -1;
  grid-column: 1;
}
figure > video {
  grid-row: 1 / -1;
  grid-column: 1;
}
@media only screen and (max-width: 768px) {
  .gallery-container {
    column-count: 1;
  }
  figure {
    place-items: center;
  }
}
</style>
