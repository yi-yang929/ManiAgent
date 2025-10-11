<script>
import { Swiper, SwiperSlide} from 'swiper/vue';
import { Navigation, Pagination, Autoplay} from 'swiper/modules';
import 'swiper/css/bundle';

export default {
  components: {
      Swiper,
      SwiperSlide,
      Navigation,
      Pagination,
      Autoplay,
    },
  data() {
    return {
      modules: [
        Navigation,
        Pagination,
        Autoplay,
      ],
      // // 选择要轮播的照片
      // image_paths: [
      //   "./carousel/1.jpg",
      //   "./carousel/2.jpg",
      //   "./carousel/3.jpg",
      //   "./carousel/4.jpg",
      //   "./carousel/5.jpg",
      //   "./carousel/6.jpg",
      // ],
      video_paths: [
        "./video/video.mp4",
        "./video/video.mp4",
        "./video/video.mp4",
        "./video/video.mp4",
        "./video/video.mp4",
      ]
    }
  }
}
</script>

<template>
  <el-row justify="center">
    <el-col :span="24">
      <!-- 设置轮播图：循环播放、首张图序号、响应式、导航和分页、自动播放 -->
      <swiper
        :loop="true"
        :slidesPerView="1"
        :breakpoints="{
          600: {
            slidesPerView: 2,
          },
          800: {
            slidesPerView: 3,
          },
        }"
        :modules="modules"
        :navigation="{ 
          hideOnClick:true,
        }"
        :pagination="{ 
          hideOnClick:true,
          clickable:true, 
          type:'bullets' 
        }"
        :autoplay="{ 
          delay:5000,
          disableOnInteraction:false,
          pauseOnMouseEnter:true,
        }"
        >
        <!-- <swiper-slide v-for="path in image_paths">
          <el-image :src="path"/>
        </swiper-slide> -->
        <swiper-slide v-for="path in video_paths">
          <video 
            controls 
            muted 
            preload 
            playsinline
            style="width: 100%; height: 100%; object-fit: cover;"
          >
            <source :src="path" type="video/mp4">
          </video>
        </swiper-slide>
      </swiper>
    </el-col>
  </el-row>
</template>
  
<style>

/* 设置Swiper风格 */
.swiper {
  --swiper-theme-color: white;
}

swiper-slide {
  height: auto;
}

video {
  aspect-ratio: 16 / 9;
  width: 100%;
}

</style>
  