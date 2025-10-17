<script>
import Title from './sections/Title.vue'
import Abstract from './sections/Abstract.vue'
import Markdown from './sections/Markdown.vue'
import BibTeX from './sections/BibTeX.vue'
import Carousel from './sections/Carousel.vue'
import Video from './sections/Video.vue'
import ImageSlider from './sections/ImageSlider.vue'
import ImageSliderInner from './sections/ImageSliderInner.vue'
import ImageSelector from './sections/ImageSelector.vue'
import Echart from './sections/Echart.vue'
import Table from './sections/Table.vue'
import Collapse from './sections/Collapse.vue'
import SeletionForComparison from './sections/SeletionForComparison.vue'
import Comment from './sections/Comment.vue'
import Latex from './sections/Latex.vue'
import Model3D from './sections/Model3D.vue'
import GaussianSplats3D from './sections/GaussianSplats3D.vue'
import Carousel_simulation from './sections/Carousel_simulation.vue'
import Carousel_datacollect from './sections/Carousel_datacollect.vue'
// import { createApp } from 'vue'
// import App from './App.vue'
// import VueGtag from 'vue-gtag'
// const app = createApp(App)

// app.use(VueGtag, {
//   config: {
//     id: 'G-XXXXXXXXXX' // 替换为你的测量 ID
//   }
// })

// app.mount('#app')

export default {
  components: {
    Title,
    Abstract,
    Markdown,
    BibTeX,
    Carousel,
    Video,
    ImageSlider,
    ImageSliderInner,
    ImageSelector,
    Echart,
    Collapse,
    Table,
    SeletionForComparison,
    Comment,
    Latex,
    Model3D,
    GaussianSplats3D,
    Carousel_simulation,
    Carousel_datacollect
  }
}
</script>

<template>
  <Title/>
  <!-- <Carousel/> -->
  <Video/>
  <Abstract/>
  <!-- <Markdown/> -->
  <Carousel_simulation/>
  <Carousel/>
  <Carousel_datacollect/>
  <!-- <Latex/> -->
  <Table/>
  <!-- <Collapse/> -->
  <!-- <Echart/> -->
  <!-- <Model3D/> -->
  <!-- <GaussianSplats3D/> -->
  <!-- <SeletionForComparison/> -->
  <!-- <ImageSliderInner/> -->
  <!-- <ImageSlider/> -->
  <!-- <ImageSelector/> -->
  <BibTeX/>
  <!-- <Comment/> -->
</template>