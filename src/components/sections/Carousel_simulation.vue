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
        "./video/simulation_task_1.mp4",
        "./video/simulation_task_2.mp4",
        "./video/simulation_task_3.mp4",
        "./video/simulation_task_4.mp4",
      ]
    }
  }
}
</script>

<template>
  <div>
    <el-divider />
    
    <el-row justify="center">
      <h1 class="section-title">Simulation Experiments</h1>
    </el-row>

    <el-row justify="center">
      <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="10" >
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
  </div>
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

/* 添加标题和轮播图之间的间距 */
.section-title {
  margin-bottom: 2rem;  /* 增加标题下方间距 */
}

.carousel-container {
  margin-top: 1rem;  /* 轮播图容器上方间距 */
}

</style>
  